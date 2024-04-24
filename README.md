# Challenge 3dfilestore

In this challenge, you will design the REST API of a 3D file repository application.

We require an [OpenAPI](https://www.openapis.org) v3 specification for the undermentioned CRUD operations.

**Only one specific operation** should be implemented in TypeScript in a Node.js server.

## Features

### OpenAPI v3 Specification

The specification should describe the following features:

- List all 3D files
- Rename file
- Delete file
- Upload a 3D file
- Download original file
- Download transformed file **(only this one should be implemented)**

### Implementation

We require a single backend endpoint that implements the file transformation feature ([see below](#Transform-and-Download-feature)).

In this test, your endpoint should only transform this source file: [buggy.obj](https://storage.googleapis.com/corp-dev-challenge-3dfilestore-assets/buggy.obj).

You can use the framework of your choosing.

#### Transform and Download feature

This feature is a special functionality that will transform each vertices in the file with a given scale and translation vector.

For example with an _obj_ the vertices are described like this:

```obj
v 1  1  1
v 1  0  1
v 2 10 10
```

The transform feature will allow you to download the file with a dynamic scale and translation vectors.
For example, if we specify `[2, 2, 2]` as a scale vector, the file will be downloaded and transformed like that:

```obj
v 2  2  2
v 2  0  2
v 4 20 20
```

With a `[10, 0, 0]` as a translation vector, the file will be downloaded and transformed like that:

```obj
v 11  1  1
v 11  0  1
v 12 10 10
```

> ⚠️ The transformed file should not alter the original file! ⚠️

## Constraints

Your server should be efficient performance-wise:

- should not exceed ~512Mb of memory usage
- should support multiple clients at the same time

## Goals

You should provide:

- An [OpenAPI](https://www.openapis.org) v3 specification file for your REST operations
- The implementation _(matching your OpenAPI specification)_ of the file transformation feature in a standalone backend code written in `Typescript`

> ⚠️ Please provide your project as a Git repository without making a pull request on our own [repository](https://github.com/3dverse/challenge-3dfilestore)! ⚠️

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](https://github.com/3dverse/challenge-3dfilestore-web/blob/main/LICENSE) file for details.
