# realm-code-model

The parent types every code realm shares, the way `Memory` is shared by every memory system.

| File | Types |
|---|---|
| `types/code.yml` | `Package`, `CodeType`, `Field`, `Method`, `Call`, `FieldAccess` (compiled code); `Source`, `SourceSpan`, `SourceDeclaration`, `CallSite`, `SourceReference`, `SourceImport`, `SourceLocal` (source); `StackFrame`, `ThrownException` (a running program's failures) |
| `types/artifact.yml` | `Artifact`, `Dependency`, `Licence`, for any package ecosystem |

They declare the contract only: the properties every language's rows carry under these names. A
language realm declares its own children (`PythonDeclaration` with `parents: [SourceDeclaration]`)
over its own producers, and since a child's node carries its parents' labels, one query on a parent
reads every installed language.

## Who needs it

Install this realm with any of these. Until realms can declare what they require, each says so in
its README:

- [realm-polyglot-code](https://github.com/embabel-worlds/realm-polyglot-code): fourteen languages, read live
- [realm-java-project](https://github.com/embabel-worlds/realm-java-project): a Maven project's source and build
- [realm-java-source-code](https://github.com/embabel-worlds/realm-java-source-code): Java source with resolved types
- [realm-java-code](https://github.com/embabel-worlds/realm-java-code): compiled Java in jars
- [realm-jvm-logs](https://github.com/embabel-worlds/realm-jvm-logs): JVM log events and their stack traces

A realm whose parent is missing still loads, with a warning that names the parent; its own labels
work, and queries on the parent find none of its rows.

## Why it is not in the default world

These types used to ship in every world's standard model. Most worlds never read code, so they now
arrive with the first realm that needs them.

## Install

```
install_realm https://github.com/embabel-worlds/realm-code-model
```
