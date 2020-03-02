FROM norionomura/swift:514
LABEL maintainer "Alessandro Calzavara <alessandro.calzavara@gmail.com>"

ENV STRINGSLINT_REVISION="support-linux-execution"

# Install StringsLint
RUN git clone --branch $STRINGSLINT_REVISION https://github.com/dral3x/StringsLint.git && \
    cd StringsLint && \
    swift build --configuration release --static-swift-stdlib && \
    mv `swift build --configuration release --static-swift-stdlib --show-bin-path`/stringslint /usr/bin && \
    cd .. && \
    rm -rf StringsLint

# Print Installed StringsLint Version
RUN stringslint version
CMD ["stringslint", "lint"]