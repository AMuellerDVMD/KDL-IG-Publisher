FROM eclipse-temurin:21-jdk-jammy

# Install base tools, fonts, and Ruby for Jekyll
RUN apt-get update && apt-get install -y --no-install-recommends \
      curl ca-certificates unzip git \
      fonts-dejavu fonts-liberation fontconfig \
      ruby ruby-dev build-essential \
      bash-completion \
    && rm -rf /var/lib/apt/lists/*

# Install Jekyll and Bundler
RUN gem install jekyll bundler

# Install Node 20 via NodeSource (fix for SUSHI)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
 && apt-get update && apt-get install -y nodejs \
 && npm i -g fsh-sushi

# Install fhir-pkg-tool latest release
RUN curl -fsSL https://github.com/Gefyra/fhir-pkg-tool/releases/latest/download/fhir-pkg-tool.jar \
      -o /opt/fhir-pkg-tool.jar \
 && chmod 644 /opt/fhir-pkg-tool.jar \
 && printf '#!/usr/bin/env bash\nexec java -jar /opt/fhir-pkg-tool.jar "$@"\n' > /usr/local/bin/fhir-pkg-tool \
 && chmod +x /usr/local/bin/fhir-pkg-tool

# Set workdir to match VSCode default mount
WORKDIR /workspaces

# Create unprivileged user
RUN useradd -m runner \
 && mkdir -p /workspaces \
 && chown -R runner:runner /workspaces \
 && chsh -s /bin/bash runner \
 && echo '[ -f /usr/share/bash-completion/bash_completion ] && . /usr/share/bash-completion/bash_completion' >> /home/runner/.bashrc
USER runner
