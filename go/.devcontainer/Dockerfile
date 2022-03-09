ARG VARIANT
FROM mcr.microsoft.com/vscode/devcontainers/go:0-${VARIANT}

ARG REMOTE_USER
ARG NODE_VERSION=""
ARG GLOBAL_PKG=""
RUN git clone https://github.com/zsh-users/zsh-autosuggestions.git /home/${REMOTE_USER}/.oh-my-zsh/custom/plugins/zsh-autosuggestions \
    && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git /home/${REMOTE_USER}/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting \
    && sed -i 's/plugins=(/plugins=(zsh-autosuggestions zsh-syntax-highlighting /g' /home/${REMOTE_USER}/.zshrc \
    && if [ "${NODE_VERSION}" != "" ]; then su ${REMOTE_USER} -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION}"; fi \
    && if [ "${GLOBAL_PKG}" != "" ]; then su ${REMOTE_USER} -c "npm i -g ${GLOBAL_PKG}"; fi
