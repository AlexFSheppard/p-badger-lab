FROM ruby:3.2-bullseye

# Install common build tools and node to support jekyll, bundler, and npm/yarn tasks
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       build-essential \
       git \
       curl \
       ca-certificates \
       nodejs \
       npm \
    && rm -rf /var/lib/apt/lists/*

# Install yarn and bundler
RUN npm install -g yarn@1 || true
RUN gem install bundler || true

WORKDIR /workspace

CMD ["bash"]
