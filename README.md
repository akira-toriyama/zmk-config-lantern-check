# zmk-config-lantern-check

A ZMK user config in the shape of
[ZMK's template](https://github.com/zmkfirmware/unified-zmk-config-template),
with the [zmk-lantern](https://github.com/akira-toriyama/zmk-lantern) module
added the way its README says: ZMK's own Corne shield on the nice!nano, the
left half a split central with the module's host port, built by ZMK's
reusable workflow on every push. It is the check that the README's recipe
builds with ZMK's standard CI; it is not a keyboard's firmware (the LED
positions are a stand-in).

- [config/west.yml](config/west.yml): ZMK at `main`, the module pinned by
  commit.
- [config/corne.dtsi](config/corne.dtsi), included by both halves' overlays:
  the strip, the key under each LED, and the split's behavior nodes.
- [config/corne_left.overlay](config/corne_left.overlay),
  [config/corne_left.conf](config/corne_left.conf): the central half's CDC ACM
  port, which the nice!nano's devicetree lacks.
- [config/corne.conf](config/corne.conf): the underglow off, two colours, two
  effects, an intro, the tempo.
