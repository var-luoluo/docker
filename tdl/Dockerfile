From ubuntu:latest

RUN apt-get update \
    && apt-get install -y curl wget xz-utils jq sed \
    && rm -rf /var/lib/apt/lists/*  \
    && curl -sSL https://docs.iyear.me/tdl/install.sh | bash
RUN version=$(curl -sSL https://raw.githubusercontent.com/var-luoluo/scripts/main/bash/get_latest_version.sh | \
    bash -s telegramdesktop tdesktop) \
    && echo "$version" \
    && version=$(echo "$version" | sed 's/^v//') \
    && wget https://telegram.org/dl/desktop/linux/tsetup.{$version}.tar.xz \
    && tar -xJf tsetup.{$version}.tar.xz \
    && rm tsetup.{$version}.tar.xz

CMD ["/bin/bash"]
