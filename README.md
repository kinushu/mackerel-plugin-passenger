# mackerel-plugin-passenger

## Notice

This repository is a fork of [nabewata07/mackerel-plugin-passenger](https://github.com/nabewata07/mackerel-plugin-passenger).
It adds support for building binaries on the arm64 architecture.

## Install

```
% mkr plugin install kinushu/mackerel-plugin-passenger@v0.0.11
```

## Setting

### If you can see passenger status by simply executing `passenger-status`

```
[plugin.metrics.passenger]
command = "/path/to/mackerel-plugin-passenger"
```

### If you use bundler

```
[plugin.metrics.passenger]
command = "/path/to/mackerel-plugin-passenger -work-dir '/path/to/application_root' -bundle-path '/path/to/command/bundle'"
```

### If you use bundler and need to specify `passenger-status` path

```
[plugin.metrics.passenger]
command = "/path/to/mackerel-plugin-passenger -work-dir '/path/to/application_root' -bundle-path '/path/to/command/bundle' -status-pash '/path/to/command/passenger-status'"
```

## How to build

```shell
% make setup
% goreleaser release --snapshot --skip-publish --clean
```
