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

`fieany?Type?`

Expands to

```
A<[type]>._
```

**Examples**

`fieanyi` will expand to `A<int>._`<br />
`fieanys` will expand to `A<string>._`<br />
`fieanyd8` will expand to `A<DateTime>._`

**Template**

```
«:ufie»A<«?Get(Type)»>._
```

####Versions####
| Ver        | Date           | Description of change  |
| :-----------: |-------------| :-----|
| 1      | 2013-FEB-09 | Initial Commit |
| 2      | 2013-FEB-10 | Changed `fieu` to `ufie` and started using AddNameSpace (thanks to [@RoryBecker](http://twitter.com/RoryBecker) at DevExpress for the suggestions) |
| 3      | 2013-FEB-13 | Title missing from `Any string` in README |
| 4      | 2013-FEB-17 | Removed `fieanyi` and `fieanys`. Replaced with `fieany?Type?` |
