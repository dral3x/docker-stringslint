FROM norionomura/swift:54
LABEL maintainer "Alessandro Calzavara <alessandro.calzavara@gmail.com>"

ENV STRINGSLINT_REVISION="0.1.6"

# Install StringsLint
RUN git clone --branch $STRINGSLINT_REVISION https://github.com/dral3x/StringsLint.git
WORKDIR /StringsLint
ARG SWIFT_FLAGS="--configuration release --static-swift-stdlib"
RUN swift build $SWIFT_FLAGS --product stringslint
RUN mv `swift build $SWIFT_FLAGS --show-bin-path`/stringslint /usr/bin
WORKDIR /
RUN rm -rf StringsLint

# Print StringsLint Version
RUN stringslint version
CMD ["stringslint", "lint"]