# Cradio

Cradio is a firmware for a few 34 key keyboards, including Cradio, Hypergolic and Sweep.

## Pin arrangement

Some revisions of the aforementioned PCBs have slightly different pin arrangements compared to what's defined in [`cradio.dtsi`](./cradio.dtsi). If you need to swap a few keys for your particular PCB, you can easily reorder the `input-gpio` definition in your own keymap file (i.e. in `zmk-config/config/cradio.keymap`):

```dts
/* Adjusted Cradio pin arrangement */
/* The position of Q and B keys have been swapped */
&kscan0 {
    input-gpios
            = <&gpio0 6  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 8  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 17 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 20 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 22 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 24 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 0  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 11 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 4  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 6  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 31 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 29 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 02 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 15 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 13 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 11 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 10 (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio0 9  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 1  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 2  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
            , <&gpio1 7  (GPIO_ACTIVE_LOW | GPIO_PULL_UP)>
    ;
};
```

This `&kscan0` block must be placed outside of any blocks surrounded by curly braces (`{...}`).
