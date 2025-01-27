# OCaml Multiplayer Games

# Useful cmds
dune build
dune test

(modes js)

opam repo add with-extensions https://github.com/janestreet/opam-repository.git#with-extensions --dont-select
opam update
opam switch create 5.2.0+flambda2 --repos with-extensions,default 
eval $(opam env --switch=5.2.0+flambda2)
opam install --yes  ocamlformat.0.26.2+jst  merlin.5.2.1-502+jst  ocaml-lsp-server.1.19.0+jst  dune

opam install --deps-only ./bonsai_examples.opam 

# Links
https://dune.readthedocs.io/en/latest/
https://ocsigen.org/js_of_ocaml/
https://github.com/janestreet/bonsai_web/blob/master/docs/guide/00-introduction.md


Clone the repo and open with https://github.com/codespaces
It has an OCaml development environment using Docker. 
It's based on the `ocaml/opam` Docker image.
