# zmk-config-lantern-check

A ZMK user config in the shape of
[ZMK's template](https://github.com/zmkfirmware/unified-zmk-config-template),
with the [zmk-vfx-lantern](https://github.com/akira-toriyama/zmk-vfx-lantern) module
and the broadcaster of [zmk-vfx-beacon](https://github.com/akira-toriyama/zmk-vfx-beacon)
added the way their READMEs say: ZMK's own Corne shield on the nice!nano, the
left half a split central with zmk-vfx-lantern's host port and zmk-vfx-beacon's status
advertisement, built by ZMK's reusable workflow on every push. It is the check
that the READMEs' recipes build with ZMK's standard CI; it is not a keyboard's
firmware (the LED positions are a stand-in).

- [config/west.yml](config/west.yml): ZMK at `main`, the modules pinned by
  commit.
- [config/corne.dtsi](config/corne.dtsi), included by both halves' overlays:
  the strip, the key under each LED, and the split's behavior nodes.
- [config/corne_left.overlay](config/corne_left.overlay),
  [config/corne_left.conf](config/corne_left.conf): the central half's CDC ACM
  port, which the nice!nano's devicetree lacks, the battery fetching, and
  zmk-vfx-beacon's broadcaster with its 1200 baud entry.
- [config/corne.conf](config/corne.conf): the underglow off, two colours, two
  effects, an intro, the tempo.
