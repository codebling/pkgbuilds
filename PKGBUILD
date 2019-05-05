# Maintainer: Julien Nicoulaud <julien dot nicoulaud at gmail dot com>

pkgname=gotify-cli
pkgver=2.1.0
pkgrel=1
pkgdesc='A command line interface for pushing messages to gotify/server.'
arch=('i686' 'x86_64' 'armv7h' 'armv6h' 'aarch64')
url='https://github.com/gotify/cli'
license=('MIT')
makedepends=('go-pie' 'make' 'git')
provides=("${pkgname}")
conflicts=("${pkgname}-git")
source=("https://github.com/gotify/cli/archive/v${pkgver}.tar.gz")
sha256sums=('d6ef90b95f04bd4fe7d751bd1cbf2ff18e926c0b1d16da6b54f2d189dc3caa6b')

build() {
  cd "${srcdir}/cli-${pkgver}"
  export GOFLAGS="-gcflags=all=-trimpath=${PWD} -asmflags=all=-trimpath=${PWD} -ldflags=-extldflags=-zrelro -ldflags=-extldflags=-znow -ldflags=-X=main.Version=${pkgver}"
  go build -o build/gotify cli.go
}

package() {
  cd "${srcdir}/cli-${pkgver}"
  install -D -m755 build/gotify "${pkgdir}/usr/bin/gotify"
}

