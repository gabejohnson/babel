These are the Flow AST node types.

- [Flow objects](#flow-objects)
- [Annotations](#annotations)
  - [TypeAnnotation](#typeannotation)
  - [AnyTypeAnnotation](#anytypeannotation)
  - [ArrayTypeAnnotation](#arraytypeannotation)
  - [BooleanTypeAnnotation](#booleantypeannotation)
  - [BooleanLiteralTypeAnnotation](#booleanliteraltypeannotation)
  - [ExistsTypeAnnotation](#existstypeannotation)
  - [FunctionTypeAnnotation](#functiontypeannotation)
  - [GenericTypeAnnotation](#generictypeannotation)
  - [IntersectionTypeAnnotation](#intersectiontypeannotation)
  - [MixedTypeAnnotation](#mixedtypeannotation)
  - [EmptyTypeAnnotation](#emptytypeannotation)
  - [NullableTypeAnnotation](#nullabletypeannotation)
  - [NullLiteralTypeAnnotation](#nullliteraltypeannotation)
  - [NumberLiteralTypeAnnotation](#numberliteraltypeannotation)
  - [NumberTypeAnnotation](#numbertypeannotation)
  - [ObjectTypeAnnotation](#objecttypeannotation)
  - [StringLiteralTypeAnnotation](#stringliteraltypeannotation)
  - [StringTypeAnnotation](#stringtypeannotation)
  - [ThisTypeAnnotation](#thistypeannotation)
  - [TupleTypeAnnotation](#tupletypeannotation)
  - [TypeofTypeAnnotation](#typeoftypeannotation)
  - [UnionTypeAnnotation](#uniontypeannotation)
  - [VoidTypeAnnotation](#voidtypeannotation)
- [Declarations](#declarations)
  - [DeclareClass](#declareclass)
  - [DeclareFunction](#declarefunction)
  - [DeclareInterface](#declareinterface)
  - [DeclareModule](#declaremodule)
  - [DeclareModuleExports](#declaremoduleexports)
  - [DeclareTypeAlias](#declaretypealias)
  - [DeclareOpaqueType](#declareopaquetype)
  - [DeclareVariable](#declarevariable)
  - [DeclareExportDeclaration](#declareexportdeclaration)
  - [DeclareExportAllDeclaration](#declareexportalldeclaration)
  - [InterfaceDeclaration](#interfacedeclaration)
  - [OpaqueType](#opaquetype)
  - [TypeAlias](#typealias)
- [Predicates](#predicates)
  - [DeclaredPredicate](#declaredpredicate)
  - [InferredPredicate](#inferredpredicate)
- [Whitespaceable](#whitespaceable)
  - [ObjectTypeCallProperty](#objecttypecallproperty)
  - [ObjectTypeIndexer](#objecttypeindexer)
  - [ObjectTypeProperty](#objecttypeproperty)
  - [ObjectTypeSpreadProperty](#objecttypespreadproperty)
- [Type Parameters](#type-parameters)
  - [TypeParameter](#typeparameter)
  - [TypeParameterDeclaration](#typeparameterdeclaration)
  - [TypeParameterInstantiation](#typeparameterinstantiation)
- [Misc](#misc)
  - [ClassImplements](#classimplements)
  - [FunctionTypeParam](#functiontypeparam)
  - [InterfaceExtends](#interfaceextends)
  - [QualifiedTypeIdentifier](#qualifiedtypeidentifier)
  - [TypeCastExpression](#typecastexpression)
  - [Variance](#variance)


# Flow

```js
interface Flow <: Node {}
```

```js
interface FlowType <: Flow {}
```

# Annotations

```js
interface FlowBaseAnnotation <: FlowType {}
```

## TypeAnnotation

```js
interface TypeAnnotation <: Flow {
  type: "TypeAnnotation"
  typeAnnotation: FlowType
}
```

## AnyTypeAnnotation

```js
interface AnyTypeAnnotation <: FlowBaseAnnotation {
  type: "AnyTypeAnnotation"
}
```

## ArrayTypeAnnotation

```js
interface ArrayTypeAnnotation <: FlowType {
  type: "ArrayTypeAnnotation"
  elementType: FlowType
}
```

## BooleanTypeAnnotation

```js
interface BooleanTypeAnnotation <: FlowBaseAnnotation {
  type: "BooleanTypeAnnotation"
}
```

## BooleanLiteralTypeAnnotation

```js
interface BooleanLiteralTypeAnnotation <: FlowType {
  type: "BooleanLiteralTypeAnnotation",
  value: boolean
}
```

## ExistsTypeAnnotation 

```js
interface ExistsTypeAnnotation <: FlowType {
  type: "ExistsTypeAnnotation"
}
```

## FunctionTypeAnnotation 

```js
interface FunctionTypeAnnotation <: FlowType {
  type: "FunctionTypeAnnotation",
  typeParameters: TypeParameterDeclaration | null,
  params: [ FunctionTypeParam ],
  rest: FunctionTypeParam | null
  returnType: FlowType
}
```

## GenericTypeAnnotation 

```js
interface GenericTypeAnnotation <: FlowType {
  type: "GenericTypeAnnotation",
  id: Identifier,
  typeParameters: TypeParameterInstantiation | null
}
```

## IntersectionTypeAnnotation 

```js
interface IntersectionTypeAnnotation <: FlowType {
  type: "IntersectionTypeAnnotation",
  types: [ FlowType ]
}
```

## MixedTypeAnnotation 

```js
interface MixedTypeAnnotation <: FlowBaseAnnotation {
  type: "MixedTypeAnnotation"
}
```

## EmptyTypeAnnotation

```js
interface EmptyTypeAnnotation <: FlowBaseAnnotation {
  type: "EmptyTypeAnnotation"
}
```

## NullableTypeAnnotation

```js
interface NullableTypeAnnotation <: FlowType {
  type: "NullableTypeAnnotation",
  typeAnnotation: FlowType
}
```

## NullLiteralTypeAnnotation

```js
interface NullLiteralTypeAnnotation <: FlowBaseAnnotation {
  type: "NullLiteralTypeAnnotation"
}
```

## NumberLiteralTypeAnnotation

```js
interface NumberLiteralTypeAnnotation <: FlowType {
  type: "NumberLiteralTypeAnnotation",
  value: number
}
```

## NumberTypeAnnotation

```js
interface NumberTypeAnnotation <: FlowBaseAnnotation {
  type: "NumberTypeAnnotation"
}
```

## ObjectTypeAnnotation

```js
interface ObjectTypeAnnotation <: FlowType {
  type: "ObjectTypeAnnotation",
  properties: [ ObjectTypeProperty | ObjectTypeSpreadProperty ],
  indexers: [ ObjectTypeIndexer | null ],
  callProperties: [ ObjectTypeCallProperty | null ],
  exact: {
    validate: boolean,
    default: false
  }
}
```

## StringLiteralTypeAnnotation

```js
interface StringLiteralTypeAnnotation <: FlowType {
  type: "StringLiteralTypeAnnotation",
  value: string
}
```

## StringTypeAnnotation

```js
interface StringTypeAnnotation <: FlowBaseAnnotation {
  type: "StringTypeAnnotation"
}
```

## ThisTypeAnnotation

```js
interface ThisTypeAnnotation <: FlowBaseAnnotation {
  type: "ThisTypeAnnotation"
}
```

## TupleTypeAnnotation

```js
interface TupleTypeAnnotation <: FlowType {
  type: "TupleTypeAnnotation",
  types: [ FlowType ]
}
```

## TypeofTypeAnnotation

```js
interface TypeofTypeAnnotation <: FlowType {
  type: "TypeofTypeAnnotation",
  argument: FlowType
}
```

## UnionTypeAnnotation

```js
interface UnionTypeAnnotation <: FlowType {
  type: "UnionTypeAnnotation",
  types: [ FlowType ]
}
```

## VoidTypeAnnotation

```js
interface VoidTypeAnnotation <: FlowBaseAnnotation {
  type: "VoidTypeAnnotation"
}
```

# Declarations

```js
interface FlowDeclaration <: Flow, Declaration {}
```

## DeclareClass

```js
interface DeclareClass <: FlowDeclaration {
  type: "DeclareClass",
  id: Identifier,
  typeParameters: [ TypeParameterInstantiation ],
  extends: [ InterfaceExtends | null ],
  mixins: [ InterfaceExtends | null ],
  implements: [ ClassImplements | null ],
  body: ObjectTypeAnnotation
}
```

## DeclareFunction

```js
interface DeclareFunction <: FlowDeclaration {
  type: "DeclareFunction",
  id: Identifier,
  predicate: DeclaredPredicate | null
}
```

## DeclareInterface

```js
interface DeclareInterface <: FlowDeclaration {
  type: "DeclareInterface",
  id: Identifier,
  typeParameters: [ TypeParameter ],
  extends: [ InterfaceExtends | null ],
  mixins: [ InterfaceExtends | null ],
  implements: [ ClassImplements | null ],
  body: ObjectTypeAnnotation
}
```

## DeclareModule

```js
interface DeclareModule <: FlowDeclaration {
  type: "DeclareModule",
  id: Identifier,
  body: BlockStatement,
  kind: CommonJS | ES | null
}
```

## DeclareModuleExports

```js
interface DeclareModuleExports <: FlowDeclaration {
  type: "DeclareModuleExports",
  typeAnnotation: TypeAnnotation
}
```

## DeclareTypeAlias

```js
interface DeclareTypeAlias <: FlowDeclaration {
  type: "DeclareTypeAlias",
  id: Identifier,
  typeParameters: TypeParameterDeclaration | null,
  right: FlowType
}
```

## DeclareOpaqueType

```js
interface DeclareOpaqueType <: FlowDeclaration {
  type: "DeclareOpaqueType",
  id: Identifier,
  typeParameters: TypeParameterDeclaration | null,
  supertype: FlowType | null
}
```

## DeclareVariable

```js
interface DeclareVariable <: FlowDeclaration {
  type: "DeclareVariable",
  id: Identifier
}
```

## DeclareExportDeclaration

```js
interface DeclareExportDeclaration <: FlowDeclaration {
  type: "DeclareExportDeclaration",
  declaration: Flow | null,
  specifiers: [ ExportSpecifier | ExportNamespaceSpecifier | null ],
  source: StringLiteral | null,
  default: boolean | null
}
```

## DeclareExportAllDeclaration

```js
interface DeclareExportAllDeclaration <: FlowDeclaration {
  type: "DeclareExportAllDeclaration",
  source: StringLiteral,
  exportKind: "type" | "value" | null
}
```

## InterfaceDeclaration

```js
interface InterfaceDeclaration <: FlowDeclaration {
  type: "InterfaceDeclaration",
  id: Identifier,
  typeParameters: [ TypeParameter ],
  extends: [ InterfaceExtends | null ],
  mixins: [ InterfaceExtends | null ],
  implements: [ ClassImplements | null ],
  body: ObjectTypeAnnotation
}
```

## OpaqueType

```js
interface OpaqueType <: FlowDeclaration {
  type: "OpaqueType",
  id: Identifier,
  typeParameters: TypeParameterDeclaration | null,
  supertype: FlowType | null,
  impltype: FlowType
}
```

## TypeAlias

```js
interface TypeAlias <: FlowDeclaration {
  type: "TypeAlias",
  id: Identifier,
  typeParameters: TypeParameterDeclaration | null,
  right: FlowType
}
```

# Predicates

## DeclaredPredicate

```js
interface DeclaredPredicate <: FlowPredicate {
  type: "DeclaredPredicate",
  value: Flow
}
```

## InferredPredicate

```js
interface InferredPredicate <: FlowPredicate {
  type: "InferredPredicate"
}
```

# Whitespaceable

## ObjectTypeCallProperty

```js
interface ObjectTypeCallProperty <: UserWhitespacable {
  type: "ObjectTypeCallProperty",
  value: FlowType,
  static: boolean
}
```

## ObjectTypeIndexer

```js
interface ObjectTypeIndexer <: UserWhitespacable {
  type: "ObjectTypeIndexer",
  id: Identifier | null,
  key: FlowType,
  value: FlowType,
  static: boolean,
  variance: Variance
}
```

## ObjectTypeProperty

```js
interface ObjectTypeProperty <: UserWhitespacable {
  type: "ObjectTypeProperty",
  key: Identifier | StringLiteral,
  value: FlowType,
  kind: "init" | "get" | "set",
  static: boolean,
  optional: boolean,
  variance: Variance | null
}
```

## ObjectTypeSpreadProperty

```js
interface ObjectTypeSpreadProperty <: UserWhitespacable {
  type: "ObjectTypeSpreadProperty",
  argument: FlowType
}
```

# Type Parameters

## TypeParameter

```js
interface TypeParameter <: Flow {
  type: "TypeParameter",
  name: string,
  bound: TypeAnnotation | null,
  default: FlowType | null,
  variance Variance | null
}
```

## TypeParameterDeclaration

```js
interface TypeParameterDeclaration <: Flow {
  type: "TypeParameterDeclaration",
  params: [ TypeParameter ]
}
```

## TypeParameterInstantiation

```js
interface TypeParameterInstantiation <: Flow {
  type: "TypeParameterInstantiation",
  params: [ FlowType ]
}
```

# Misc

## ClassImplements

```js
interface ClassImplements <: Flow {
  type: "ClassImplements",
  id: Identifier,
  typeParameters: TypeParameterInstantiation | null
}
```

## FunctionTypeParam

```js
interface FunctionTypeParam <: Flow {
  type: "FunctionTypeParam",
  name: Identifier,
  typeAnnotation: FlowType,
  optional: boolean | null
}
```

## InterfaceExtends

```js
interface InterfaceExtends <: Flow {
  type: "InterfaceExtends",
  id: Identifier,
  typeParameters: TypeParameterInstantiation | null
}
```

## QualifiedTypeIdentifier

```js
interface QualifiedTypeIdentifier <: Flow {
  type: "QualifiedTypeIdentifier",
  id: Identifier,
  qualification: Identifier | QualifiedTypeIdentifier
}
```

## TypeCastExpression

```js
interface TypeCastExpression <: Flow, ExpressionWrapper {
  type: "TypeCastExpression",
  expression: Expression,
  typeAnnotation: TypeAnnotation
}
```

## Variance

```js
interface Variance <: Flow {
  type: "Variance",
  kind: "minus" | "plus"
}
```
