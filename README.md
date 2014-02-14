fakeiteasy-coderush-templates
=============================

A group of CodeRush templates to use with FakeItEasy.

###Template Expansions###

#####Setup FakeItEasy using#####

`ufie`

Expands to

```
using FakeItEasy;
```

**Template**

```
«AddNamespace(FakeItEasy)»
```

#####Create a fake object#####

`fief`

Expands to

```
var mockClassToMock = A.Fake<IClassToMock>();```

**Usage**: The `ClassToMock` field will be selected and editing will cause all instances to change. 

**Template**  

```
«:ufie»var mock«Caret»«FieldStart»«Link(ClassToMock)»«FieldEnd»«BlockAnchor» = A.Fake<I«Link(ClassToMock)»>();
```

#####Set up a call to return a value#####

`fiecr`

Expands to

```
var mockClassToMock = A.Fake<IClassToMock>();A.CallTo(() => mockClassToMock.Method(Params).Returns(ValueToReturn);
```

**Usage**: The `ClassToMock` field will be selected and editing will cause all instances to change. Hit `<Enter>` to accept changes and move to `Method`, then `Params` and finally `ValueToReturn`. 

**Template** 

```
«:ufie»var mock«Caret»«FieldStart»«Link(ClassToMock)»«FieldEnd»«BlockAnchor» = A.Fake<I«Link(ClassToMock)»>();
A.CallTo(() => mock«Link(ClassToMock)».«Field(Method)»(«Field(Params)»).Returns(«Field(ValueToReturn)»);
```

####Create ignore parameters####

#####Any integer#####

`fieanyi`

Expands to

```
A<int>._
```

**Template**

```
«:ufie»A<int>._
```
#####Any string#####

`fieanys`

Expands to

```
A<string>._
```

**Template**

```
«:ufie»A<string>._
```

####Versions####
| Ver        | Date           | Description of change  |
| :-----------: |-------------| :-----|
| 1      | 2013-FEB-09 | Initial Commit |
| 2      | 2013-FEB-10 | Changed `fieu` to `ufie` and started using AddNameSpace (thanks to [@RoryBecker](http://twitter.com/RoryBecker) at DevExpress for the suggestions |
| 3      | 2013-FEB-13 | Title missing from `Any string` in README |
