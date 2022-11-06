FROM ubuntu:kinetic

RUN apt-get update && apt-get install -y \
	curl \
	git \
	sudo \
	build-essential 

RUN useradd -ms /bin/bash vscode \
	&& usermod -aG sudo vscode \
	&& echo vscode:vscode | chpasswd

RUN NONINTERACTIVE=1 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" \
	&& chown -R vscode /home/linuxbrew/.linuxbrew

WORKDIR /home/vscode
USER vscode
SHELL [ "/bin/bash", "-c" ]
RUN echo "eval \"$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)\"" >> ~/.bashrc
RUN /home/linuxbrew/.linuxbrew/bin/brew install insilica/srvc/srvc




