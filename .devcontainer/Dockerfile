FROM ubuntu:latest

RUN DEBIAN_FRONTEND=noninteractive \
  apt-get update \
  && apt-get install -y bubblewrap \
  && apt-get install -y git \
  && apt-get install -y mercurial \
  && apt-get install -y rsync \
  && apt-get install -y ssh \
  && apt-get install -y curl \
  && apt-get install -y unzip \
  && apt-get install -y make \
  && apt-get install -y build-essential \
  && apt-get install -y autoconf \
  && apt-get install -y libffi-dev \
  && apt-get install -y libgmp-dev \
  && apt-get install -y libssl-dev \
  && apt-get install -y pkg-config \
  && apt-get install -y zlib1g-dev \
  && apt-get install -y ncdu \
  && rm -rf /var/lib/apt/lists/* \
  && curl -fsSL https://opam.ocaml.org/install.sh > install_opam.sh \
  && chmod +x install_opam.sh \
  && ./install_opam.sh --download-only --version 2.3.0 \
  && mv opam-2.3.0-x86_64-linux ./opam \
  && chmod +x opam \
  && ./opam init --disable-sandboxing --auto-setup \
  && ./opam repo add with-extensions https://github.com/janestreet/opam-repository.git#with-extensions --dont-select \
  && ./opam update \
  && ./opam switch create 5.2.0+flambda2 --repos with-extensions,default \
  && eval $(./opam env --switch=5.2.0+flambda2) \
  && ./opam install --yes \
    ocamlformat.0.26.2+jst \
    merlin.5.2.1-502+jst \
    ocaml-lsp-server.1.19.0+jst \
    dune \
    async async_extra async_js async_kernel async_rpc_kernel async_rpc_websocket \
    base core core_kernel ocaml-embed-file \
    ppx_jane virtual_dom cohttp cohttp-async uri \
    bonsai js_of_ocaml-ppx \
  && apt autoremove && apt autoclean && ./opam clean && rm -rf /tmp/* \
  && eval $(./opam env --switch=5.2.0+flambda2) 
 
# I always get:
# Sys_error("No space left on device")
# I even tried: 
RUN ./opam config set jobs 1 && ./opam install --yes js_of_ocaml
# So we need to do it after the docker finished. 
