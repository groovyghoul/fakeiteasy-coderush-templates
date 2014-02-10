fakeiteasy-coderush-templates
=============================

A group of CodeRush templates to use with FakeItEasy.

###Template Expansions###

#####Setup FakeItEasy using#####

`fieu`

Expands to

```
using FakeItEasy;
```

#####Create a fake object#####

`fief`

Expands to

```
var mockClassToMock = A.Fake<IClassToMock>();```

**Usage**: The `ClassToMock` field will be selected and editing will cause all instances to change. 

**Template**:  

```
var mock«Caret»«FieldStart»«Link(ClassToMock)»«FieldEnd»«BlockAnchor» = A.Fake<I«Link(ClassToMock)»>();
```

#####Set up a call to return a value#####

`fiecr`

Expands to

```
var mockClassToMock = A.Fake<IClassToMock>();A.CallTo(() => mockClassToMock.Method(Params).Returns(ValueToReturn);
```

**Usage**: The `ClassToMock` field will be selected and editing will cause all instances to change. Hit `<Enter>` to accept changes and move to `Method`, then `Params` and finally `ValueToReturn`. 

**Template**: 

```
var mock«Caret»«FieldStart»«Link(ClassToMock)»«FieldEnd»«BlockAnchor» = A.Fake<I«Link(ClassToMock)»>();
A.CallTo(() => mock«Link(ClassToMock)».«Field(Method)»(«Field(Params)»).Returns(«Field(ValueToReturn)»);
```

####Create ignore parameters####

#####Any integer#####

`fieanyi`

Expands to

```
A<int>._
```

`fieanys`

#####Expands to#####

```
A<string>._
```

