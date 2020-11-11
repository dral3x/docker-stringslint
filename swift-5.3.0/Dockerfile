FROM norionomura/swift:53
LABEL maintainer "Alessandro Calzavara <alessandro.calzavara@gmail.com>"

ENV STRINGSLINT_REVISION="master"

# Install StringsLint
RUN git clone --branch $STRINGSLINT_REVISION https://github.com/dral3x/StringsLint.git && \
    cd StringsLint && \
    swift build --configuration release --static-swift-stdlib && \
    mv `swift build --configuration release --static-swift-stdlib --show-bin-path`/stringslint /usr/bin && \
    cd .. && \
    rm -rf StringsLint

# Print StringsLint Version
RUN stringslint version
CMD ["stringslint", "lint"]