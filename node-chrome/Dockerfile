FROM node:6.10.3

# Install Chrome
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - &&\
    sh -c 'echo "deb http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list' &&\
    apt-get update &&\
    apt-get install -y ca-certificates curl google-chrome-stable &&\
    rm /etc/apt/sources.list.d/google-chrome.list &&\
    rm -rf /var/lib/apt/lists/* /var/cache/apt/*
    