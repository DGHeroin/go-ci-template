# go-ci-template

[![Build Status](https://travis-ci.org/DGHeroin/go-ci-template.svg?branch=master)](https://travis-ci.org/DGHeroin/go-ci-template)

## Travis-CI 构建模板
```yaml
language: go
sudo: false
before_script:
  - go vet ./...
install:
  # Add Godeps dependencies to GOPATH and PATH
  - export GOPATH="${TRAVIS_BUILD_DIR}/Godeps/_workspace:$GOPATH"
  - export PATH="${TRAVIS_BUILD_DIR}/Godeps/_workspace/bin:$PATH"
```

## Travis-CI 自动部署
### macOS
```yaml
gem install travis    # 安装 travis 工具自动生成 .travis.yml
travis setup releases # 重新生成带部署的 .travis.yml
```