# VastNetStateLayout

## Version 0.0.3

- [ ] Removed `SimpleNetErrorView` and `SimpleNetLoadingView`
- [ ] Removed `VastNetLoadingView` and `VastNetErrorView` interfaces
- [x] Added `VastNetStateMgr` to manage interface listener events and layout resource settings
- [x] Design independent interfaces for four network states

## Version 0.0.2

- [x] `INetErrorView` renamed to `VastNetErrorView`
- [x] `INetLoadingView` renamed to `VastNetLoadingView`
- [x] The retry interface in `INetErrorView` is independent, and the `VastRetry` interface is added

## Version 0.0.1

- [x] Layout for setting custom network status ui