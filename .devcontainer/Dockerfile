FROM ocaml/opam:latest

# Install Opam packages
RUN opam init && \
  opam update && \
  opam install \
  base core_kernel \
  ounit qcheck dune \
  ocamlformat \
  js_of_ocaml js_of_ocaml-ppx js_of_ocaml-lwt
