FROM ocaml/opam:debian

# Install Opam packages
RUN opam update && \
  opam install \
  base core_kernel \
  ounit qcheck dune \
  ocamlformat
