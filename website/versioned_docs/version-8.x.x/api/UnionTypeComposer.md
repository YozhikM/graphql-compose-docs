---
id: version-8.x.x-UnionTypeComposer
title: UnionTypeComposer
custom_edit_url: https://github.com/graphql-compose/graphql-compose/blob/master/src/UnionTypeComposer.d.ts
original_id: UnionTypeComposer
---

<!-- 
🛑🛑🛑
DO NOT EDIT THIS FILE!
IT WAS AUTO-GENERATED FROM d.ts FILE
🛑🛑🛑
If you want to make changes in this file, please do it via
https://github.com/graphql-compose/graphql-compose/blob/master/src/UnionTypeComposer.d.ts
-->

Class that helps to create `UnionTypeComposer`s and provide ability to modify them.

## Static methods

### static create()

```js
static create<TSrc = any, TCtx = any>(
  typeDef: UnionTypeComposerDefinition<TSrc, TCtx>,
  schemaComposer: SchemaComposer<TCtx>
): UnionTypeComposer<TSrc, TCtx>
```

Create `UnionTypeComposer` with adding it by name to the `SchemaComposer`.

### static createTemp()

```js
static createTemp<TSrc = any, TCtx = any>(
  typeDef: UnionTypeComposerDefinition<TSrc, TCtx>,
  schemaComposer: SchemaComposer<TCtx>
): UnionTypeComposer<TSrc, TCtx>
```

Create `UnionTypeComposer` without adding it to the `SchemaComposer`. This method may be useful in plugins, when you need to create type temporary.

## Getters

### List

```js
List: ListComposer<UnionTypeComposer<TSource, TContext>>;
```

Get Type wrapped in List modifier

```js
const UserTC = schemaComposer.createUnionTC(`union User = Admin | Client`);
schemaComposer.Query.addFields({
  users1: { type: UserTC.List }, // in SDL: users1: [User]
  users2: { type: UserTC.NonNull.List }, // in SDL: users2: [User!]
  users3: { type: UserTC.NonNull.List.NonNull } // in SDL: users2: [User!]!
});
```

### NonNull

```js
NonNull: NonNullComposer<UnionTypeComposer<TSource, TContext>>;
```

Get Type wrapped in NonNull modifier

```js
const UserTC = schemaComposer.createUnionTC(`union User = Admin | Client`);
schemaComposer.Query.addFields({
  users1: { type: UserTC.List }, // in SDL: users1: [User]
  users2: { type: UserTC.NonNull.List }, // in SDL: users2: [User!]
  users3: { type: UserTC.NonNull.List.NonNull } // in SDL: users2: [User!]!
});
```

## Properties

### schemaComposer

```js
schemaComposer: SchemaComposer<TContext>;
```

## Union Types methods

### hasType()

```js
hasType(
  name: ObjectTypeComposerDefinition<any, TContext>
): boolean
```

### getTypes()

```js
getTypes(): Array<ObjectTypeComposerThunked<TSource, TContext>>
```

### getTypeComposers()

```js
getTypeComposers(): Array<ObjectTypeComposer<TSource, TContext>>
```

### getTypeNames()

```js
getTypeNames(): string[]
```

### clearTypes()

```js
clearTypes(): this
```

### setTypes()

```js
setTypes(
  types: ReadonlyArray<ObjectTypeComposerThunked<TSource, TContext> | ObjectTypeComposerDefinition<any, TContext>>
): this
```

### addType()

```js
addType(
  type: ObjectTypeComposerThunked<any, TContext> | ObjectTypeComposerDefinition<any, TContext>
): this
```

### addTypes()

```js
addTypes(
  types: ReadonlyArray<ObjectTypeComposerThunked<any, TContext> | ObjectTypeComposerDefinition<any, TContext>>
): this
```

### removeType()

```js
removeType(
  nameOrArray: string | string[]
): this
```

### removeOtherTypes()

```js
removeOtherTypes(
  nameOrArray: string | string[]
): this
```

## Type methods

### getType()

```js
getType(): GraphQLUnionType
```

### getTypePlural()

```js
getTypePlural(): ListComposer<UnionTypeComposer<TSource, TContext>>
```

### getTypeNonNull()

```js
getTypeNonNull(): NonNullComposer<UnionTypeComposer<TSource, TContext>>
```

### getTypeName()

```js
getTypeName(): string
```

### setTypeName()

```js
setTypeName(
  name: string
): this
```

### getDescription()

```js
getDescription(): string
```

### setDescription()

```js
setDescription(
  description: string
): this
```

### clone()

```js
clone(
  newTypeNameOrTC: string | UnionTypeComposer<any, any>
): UnionTypeComposer<any, TContext>
```

You may clone this type with a new provided name as string.
Or you may provide a new TypeComposer which will get all cloned
settings from this type.

### cloneTo()

```js
cloneTo(
  anotherSchemaComposer: SchemaComposer<any>,
  cloneMap: Map<any, any>
): UnionTypeComposer<any, any>
```

Clone this type to another SchemaComposer.
Also will be cloned all sub-types.

### merge()

```js
merge(
  type: GraphQLUnionType | UnionTypeComposer<any, any>
): this
```

## ResolveType methods

### getResolveType()

```js
getResolveType(): GraphQLTypeResolver<TSource, TContext> | undefined | null
```

### setResolveType()

```js
setResolveType(
  fn: GraphQLTypeResolver<TSource, TContext> | undefined | null
): this
```

### hasTypeResolver()

```js
hasTypeResolver(
  type: ObjectTypeComposerThunked<any, TContext> | ObjectTypeComposerDefinition<any, TContext>
): boolean
```

### getTypeResolvers()

```js
getTypeResolvers(): UnionTypeComposerResolversMap<TSource, TContext>
```

### getTypeResolverCheckFn()

```js
getTypeResolverCheckFn(
  type: ObjectTypeComposerThunked<any, TContext> | ObjectTypeComposerDefinition<any, TContext>
): UnionTypeComposerResolverCheckFn<any, TContext>
```

### getTypeResolverNames()

```js
getTypeResolverNames(): string[]
```

### getTypeResolverTypes()

```js
getTypeResolverTypes(): Array<ObjectTypeComposerThunked<any, TContext>>
```

### setTypeResolvers()

```js
setTypeResolvers(
  typeResolversMap: UnionTypeComposerResolversMapDefinition<TSource, TContext>
): this
```

### addTypeResolver()

```js
addTypeResolver(
  type: ObjectTypeComposerDefinition<any, TContext>,
  checkFn: UnionTypeComposerResolverCheckFn<TSource, TContext>
): this
```

### removeTypeResolver()

```js
removeTypeResolver(
  type: ObjectTypeComposerDefinition<any, TContext>
): this
```

### setTypeResolverFallback()

```js
setTypeResolverFallback(
  type: ObjectTypeComposer<any, TContext> | GraphQLObjectType | null
): this
```

## Extensions methods

### getExtensions()

```js
getExtensions(): Extensions
```

### setExtensions()

```js
setExtensions(
  extensions: Extensions
): this
```

### extendExtensions()

```js
extendExtensions(
  extensions: Extensions
): this
```

### clearExtensions()

```js
clearExtensions(): this
```

### getExtension()

```js
getExtension(
  extensionName: string
): unknown
```

### hasExtension()

```js
hasExtension(
  extensionName: string
): boolean
```

### setExtension()

```js
setExtension(
  extensionName: string,
  value: unknown
): this
```

### removeExtension()

```js
removeExtension(
  extensionName: string
): this
```

## Directive methods

### getDirectives()

```js
getDirectives(): Array<ExtensionsDirective>
```

### setDirectives()

```js
setDirectives(
  directives: Array<ExtensionsDirective>
): this
```

### getDirectiveNames()

```js
getDirectiveNames(): string[]
```

### getDirectiveByName()

```js
getDirectiveByName(
  directiveName: string
): DirectiveArgs | undefined
```

### getDirectiveById()

```js
getDirectiveById(
  idx: number
): DirectiveArgs | undefined
```

## Misc methods

### getNestedTCs()

```js
getNestedTCs(
  opts: {
      exclude?: string[] | undefined;
  },
  passedTypes: Set<NamedTypeComposer<any>>
): Set<NamedTypeComposer<any>>
```

Returns all types which are used inside the current type

### toSDL()

```js
toSDL(
  opts: SchemaPrinterOptions & {
      deep?: boolean;
      sortTypes?: boolean;
      exclude?: string[];
  }
): string
```

Prints SDL for current type. Or print with all used types if `deep: true` option was provided.

## Internal type definitions

### UnionTypeComposerDefinition

```js
export type UnionTypeComposerDefinition<TSource, TContext> =
  | TypeAsString
  | TypeDefinitionString
  | UnionTypeComposerAsObjectDefinition<TSource, TContext>
  | GraphQLUnionType;
```

### UnionTypeComposerAsObjectDefinition

```js
export type UnionTypeComposerAsObjectDefinition<TSource, TContext> = {
  name: string;
  types?: Thunk<ReadonlyArray<ObjectTypeComposerDefinition<any, TContext>> | null>;
  resolveType?: GraphQLTypeResolver<TSource, TContext> | null;
  description?: string | null;
  extensions?: Extensions;
};
```

### UnionTypeComposerResolversMap

```js
export type UnionTypeComposerResolversMap<TSource, TContext> = Map<
  ObjectTypeComposerThunked<TSource, TContext>,
  UnionTypeComposerResolverCheckFn<TSource, TContext>
>;
```

### UnionTypeComposerResolversMapDefinition

```js
export type UnionTypeComposerResolversMapDefinition<TSource, TContext> =
  | Map<
      ObjectTypeComposerThunked<any, TContext> | ObjectTypeComposerDefinition<any, TContext>,
      UnionTypeComposerResolverCheckFn<TSource, TContext>
    >
  | Readonly<UnionTypeComposerResolversMap<TSource, TContext>>;
```

### UnionTypeComposerResolverCheckFn

```js
export type UnionTypeComposerResolverCheckFn<TSource, TContext> = (
  value: TSource,
  context: TContext,
  info: GraphQLResolveInfo
) => MaybePromise<boolean | null | undefined>;
```

### UnionTypeComposerThunked

```js
export type UnionTypeComposerThunked<TReturn, TContext> =
  | UnionTypeComposer<TReturn, TContext>
  | ThunkComposer<UnionTypeComposer<TReturn, TContext>, GraphQLUnionType>;
```