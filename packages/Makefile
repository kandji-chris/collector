export NAME=pganalyze-collector
export VERSION=0.41.3
export GIT_VERSION=v0.41.3
#export GIT_VERSION=HEAD
#export GIT_VERSION=618e85ce5ed5365bc7d9d9da866fdeb73bac5a55
#export VERSION=$(shell git show -s --format=%ct.%h HEAD)

export RPM_PACKAGE_OUT=$(NAME)-$(VERSION)-1.x86_64.rpm
export RPM_SYSTEMD_PACKAGE=$(NAME)-$(VERSION)-1_systemd.x86_64.rpm
export DEB_PACKAGE_OUT=$(NAME)_$(VERSION)_amd64.deb
export DEB_SYSTEMD_PACKAGE=$(NAME)_$(VERSION)_systemd_amd64.deb

export TMP_DIR=$(shell pwd)/tmp

.PHONY: default setup build test clean repo

default: test repo

setup:
	mkdir -p $(TMP_DIR)

build: setup
	make -C src

test: setup build
	make -C test

repo: build
	make -C repo

clean:
	rm -rf $(TMP_DIR)
