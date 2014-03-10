# OPAM - A package manager for OCaml

OPAM is a source-based package manager for OCaml. It supports multiple simultaneous
compiler installations, flexible package constraints, and a Git-friendly development
workflow.

OPAM is created and maintained by [OCamlPro](http://www.ocamlpro.com).

To get started, checkout the [Quick
Install](http://opam.ocaml.org/doc/Quick_Install.html) guide.

## Versioning

For transparency and insight into our release cycle, and for striving
to maintain backward compatibility, OPAM will be maintained under
the Semantic Versioning guidelines as much as possible.

Releases will be numbered with the following format:

```
<major>.<minor>.<patch>
```

And constructed with the following guidelines:

* Breaking backward compatibility bumps the major (and resets the minor and patch)
* New additions without breaking backward compatibility bumps the minor (and resets the patch)
* Bug fixes and misc changes bumps the patch

For more information on SemVer, please visit http://semver.org/.

It is expected than upgrade work transparently between minor releases:
an OPAM binary with version `x.y.z` should be able to use the OCaml
packages and compilers created with OPAM version `x.(y-1).0`

## Compiling this repo

Run `./configure`

Then, there are currently two main ways to compile this repo:
* With automatic downloading of the prerequisites, and all-in-one compilation.
  Just run
  - `make`
  - `make install`
* Using the dependencies already installed. This is necessary if you want to
  install opam-lib to build other projects (opamfu, opam-rt...).
  - make sure you have ocamlgraph, cmdliner, dose 3.1.2, cudf, re >= 1.2.0 and
    ocamlfind installed. Or run `opam install opam-lib --deps-only` if you
    already have a working instance.
  - run `make prepare`. This is needed just once.
  - run `make compile`.
  - run `make install`, and `make libinstall` if you need the libraries.
* The latter is also possible without resorting to ocp-build, although it will
  take longer.
  - `make with-ocamlbuild`
  - `make install-with-ocamlbuild`
  - `make libinstall-with-ocamlbuild`

Note that this is in a transitory state right now, expect it to change for
something simpler.

## Bug tracker

Have a bug or a feature request ?
[Please open a new issue](https://github.com/ocaml/opam/issues).
Before opening any issue, please search for existing issues.

## Community

Keep track of development and community news.

* Have a question that's not a feature request or bug report?
  [Ask on the mailing list](http://lists.ocaml.org/listinfo/infrastructure).

* Chat with fellow OPAMers in IRC. On the `irc.freenode.net` server,
  in the `#ocaml` or the `#opam` channel.

## Contributing

Please submit all pull requests against the `master` branch.

## Documentation

#### User Manual

The main documentation entry point to OPAM is the user manual,
available using `opam --help`. To get help for a specific command, use
`opam <command> --help`.

#### Tutorials

A collection of tutorials are available online at <http://opam.ocaml.org>.
These tutorials are automatically generated from the
[wiki](https://github.com/ocaml/opam/wiki/_pages) and
are also available in PDF format in the `doc/tutorials` directory.

#### API, Code Documentation and Developer Manual

The API documentation is available
 [online](http://htmlpreview.github.com/?https://github.com/ocaml/opam/blob/master/doc/html/index.html)
 and under the `doc/html/` directory; the developer manual is in
 the `doc/dev-manual/` directory.

### Related repositories

- [ocaml/opam-repository](https://github.com/ocaml/opam-repository) is the official repository for OPAM packages and compilers. A number of non-official repositories are also available on the interwebs, for instance on [Github](https://github.com/search?q=opam-repo&type=Repositories).
- [opam2web](https://github.com/ocaml/opam2web) generates a collection of browsable HTML files for a given repository. It is used to generate http://opam.ocaml.org.
- [opam-rt](https://github.com/ocaml/opam-rt) is the regression framework for OPAM.
- [opamlot](https://github.com/ocamllabs/ocamlot) is the automated QA environment for OPAM. 

## Copyright and license

Copyright 2012-2014 OCamlPro  
Copyright 2012 INRIA

All rights reserved. OPAM is distributed under the terms of
the GNU Lesser General Public License version 3.0.

OPAM is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

