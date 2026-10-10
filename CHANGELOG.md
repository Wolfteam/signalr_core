## 1.2.0

- Require `equatable ^3.0.0`. `EquatableMixin` was removed upstream; `CompletionMessage`
  and `PingMessage` now mix in `Equatable` directly. Behavioural consequence verified against
  the resolved 3.0.0 source: the automatic `toString` override still exists, but is now gated
  on `stringify ?? EquatableConfig.stringify` (which defaults to `false`), so
  `CompletionMessage`/`PingMessage` `toString()` now returns the default `Instance of '...'`
  instead of the bare class name. (Note: equatable's own CHANGELOG also claims 3.0.0 drops the
  `runtimeType` check in `==`, but the published 3.0.0 source and a runtime check both show the
  `runtimeType` check is still present and enforced — two different `Equatable` subclasses with
  equal `props` still compare unequal.)
- Require `sse_channel ^0.2.2`. `SseChannel.stream` now emits `MessageEvent` objects (exported
  from `package:sse_channel/sse_channel.dart`; the fields are `data`, `event`, and `id` as
  described upstream, though the type itself is named `MessageEvent`, not `Event`), so the
  server-sent-events transport reads `event.data`.
- Bump `http` to `^1.6.0`, `web_socket_channel` to `^3.0.3`.
- Dev: `lints` to `^6.1.0`, `test` to `^1.33.0`.
- Flutter pin moved to 3.47.7.
- No public API changes.

## 1.0.0

- Initial version, created by Stagehand

## 1.0.1

- Formatting and other updates.

## 1.0.2 

- Bug fix.

## 1.0.3 

- Fixed web socket implementation. Other bugs.

## 1.0.4

- Fixed invoke method.

## 1.0.5

- Fixed typo in negotiate response - [f28f4bf](https://github.com/jamiewest/signalr_core/commit/f28f4bfa6f174dc24b2614ece057fcaaf3d121d1) 

## 1.0.6

- Bug fixes - [359e1ae](https://github.com/dart-lang/http/commit/469ea67d412d4e90ade81bc672b601d4d663e685), [ab4a902](https://github.com/jamiewest/signalr_core/commit/ab4a9020c72c5ba1f9560940fade536516cb1292), [9cfeea4](https://github.com/jamiewest/signalr_core/commit/9cfeea4a86a78ce32f29a3147cf58532415ea814)

## 1.0.7

- Bug fixes - [51cba40](https://github.com/jamiewest/signalr_core/commit/51cba400e52640b7f2fdf0dd4154061d8117e778)

## 1.0.8

- Bug Fixes - [dc767b9](https://github.com/jamiewest/signalr_core/commit/dc767b943a5cf9dee6d464cae5c7e015c99deb50)

## 1.1.0

- Null safety contributed by Mol0ko [#44](https://github.com/jamiewest/signalr_core/commit/7e8eaaf7a7940c60385a076625b75f126a1292d7)

## 1.1.1 

- Bug fixes contributed by janjoosse [#49](https://github.com/jamiewest/signalr_core/pull/49)

## 1.1.2

- Updated packages