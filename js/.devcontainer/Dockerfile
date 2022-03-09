ARG VARIANT
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-${VARIANT}

ARG REMOTE_USER
ARG GLOBAL_PKG=""
RUN git clone https://github.com/zsh-users/zsh-autosuggestions.git /home/${REMOTE_USER}/.oh-my-zsh/custom/plugins/zsh-autosuggestions \
    && git clone https://github.com/zsh-users/zsh-syntax-highlighting.git /home/${REMOTE_USER}/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting \
    && sed -i 's/plugins=(/plugins=(zsh-autosuggestions zsh-syntax-highlighting /g' /home/${REMOTE_USER}/.zshrc \
    && if [ "${GLOBAL_PKG}" != "" ]; then su ${REMOTE_USER} -c "npm i -g ${GLOBAL_PKG}"; fi
