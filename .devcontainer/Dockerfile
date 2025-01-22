FROM ocaml/opam2:4.08

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

USER root

# Install Opam packages
RUN opam update && \
  opam install \
  base core_kernel \
  ounit qcheck dune \
  ocamlformat

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog

# Add opam binaries to PATH.
ENV PATH=/home/opam/.opam/4.08/bin:$PATH
