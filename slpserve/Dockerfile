FROM christroutner/ct-base-ubuntu
LABEL Nicolai Skye <nicolaiskye@icloud.com>

RUN apt-get update -y

RUN apt-get install -y autoconf libtool

#Set the working directory to be the home directory
WORKDIR /home/safeuser

# Switch to user account.
USER safeuser
# Prep 'sudo' commands.
#RUN echo 'abcd8765' | sudo -S pwd

# Clone the Bitcore repository
WORKDIR /home/safeuser
RUN git clone https://github.com/christroutner/slpserve
#RUN git clone https://github.com/fountainhead-cash/slpserve
WORKDIR /home/safeuser/slpserve
RUN npm install

COPY startup-script.sh start.sh
CMD ["./start.sh"]

