FROM ruby:3


## ARG USERNAME=jekyll
## ARG USER_UID=1000
## ARG USER_GID=$USER_UID
## 
## # Avoid warnings by switching to noninteractive
## ENV DEBIAN_FRONTEND=noninteractive
## # Configure apt and install packages
## RUN apt-get update \
##     && apt-get -y install --no-install-recommends apt-utils dialog locales 2>&1 \
##     # Verify git, process tools installed
##     && apt-get -y install git openssh-client iproute2 procps lsb-release \
##     #
##     # Install ruby-debug-ide and debase
##     && gem install ruby-debug-ide \
##     && gem install debase \
##     #
##     # Install node.js
##     && apt-get -y install curl software-properties-common \
##     && curl -sL https://deb.nodesource.com/setup_18.x | bash - \
##     && apt-get -y install nodejs \
##     #
##     # Create a non-root user to use if preferred - see https://aka.ms/vscode-remote/containers/non-root-user.
##     && groupadd --gid $USER_GID $USERNAME \
##     && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
##     # [Optional] Add sudo support for the non-root user
##     && apt-get install -y sudo \
##     && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME\
##     && chmod 0440 /etc/sudoers.d/$USERNAME \
##     #
##     # Clean up
##     && apt-get autoremove -y \
##     && apt-get clean -y \
##     && rm -rf /var/lib/apt/lists/*
## 
## # Set the locale
## RUN sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
##     dpkg-reconfigure --frontend=noninteractive locales && \
##     update-locale LANG=en_US.UTF-8
## 
## ENV LANG en_US.UTF-8
## 
## # Switch back to dialog for any ad-hoc use of apt-get
## ENV DEBIAN_FRONTEND=dialog


#### Above is directly copied from Jekyll/.devcontainer/Dockerfile
#### Update it to remove any unnecessary steps

RUN apt-get update \
    && apt-get install -y ruby-full build-essential zlib1g-dev \
    && gem install jekyll bundler

WORKDIR /website

CMD jekyll serve --port 9999 --host 0.0.0.0
