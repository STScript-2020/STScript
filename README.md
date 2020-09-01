# STScript

This repository hosts the source code for STScript,
a toolchain for communication-safe web development in
TypeScript with Routed Multiparty Session Types.

This is an anonymised pre-artifact accompanying
the CGO paper submission.
A final artifact will be submitted for evaluation upon paper acceptance.

## Prerequisites

* [Docker](https://www.docker.com/)
* [Node.js](https://nodejs.org/en/)

## Code generation toolchain
`mpst_ts/` directory contains the code generation
toolchain which generates TypeScript APIs
from a Scribble protocol speciication.

### Getting started
You can build the development environment via

```bash
chmod +x build.sh
./build.sh
```

and enter the development environment with

```bash
docker-compose up -d
docker-compose exec codegen bash
```

To exit the development environment,
open a separate terminal window and run

```bash
docker-compose down
```

### How to use
These commands only work inside the development environment.

#### Generate Node.js APIs

To generate code for __server-side__ (Node.js) endpoints, run
```bash
./stscript.sh PATH_TO_PROTOCOL PROTOCOL ROLE node
```

e.g.

```bash
./stscript.sh protocols/Adder.scr Adder Svr node
```

The APIs will be generated under `sandbox/node/`.

#### Generate React.js APIs

To generate code for __browser-side__ (React.js) endpoints,
run
```bash
./stscript.sh PATH_TO_PROTOCOL PROTOCOL ROLE browser -s SERVER_ROLE
```

e.g.

```bash
./stscript.sh protocols/Adder Adder Client browser -s Svr
```

The APIs will be generated under `sandbox/browser/`.

#### Run tests
To test that STScript generates APIs that
type-check against the TypeScript Compiler, run
```bash
./test.sh
```

## Other contents
`protocols/` directory contains Scribble
protocols for a range of web services, including
the case studies discussed in § 5.2 and the
running example motivated in § 1.

`case-studies/` directory contains the source
code for the interactive web applications implemented in § 5.2 -- refer to the [README](case-studies/README.md) in the directory for how to run the examples.

`benchmarks/` directory contains the performance
micro-benchmarks discussed in § 5.1 -- refer to the [README](benchmarks/README.md)
in the directory for how to run the benchmark and
visualise the results.

## Contact
The authors can be reached at stscript2020_gmail.com (replace _ with @).
