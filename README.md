![](../../workflows/gds/badge.svg) ![](../../workflows/docs/badge.svg)

# What is this project about?

This project implements a monte-carlo simulation of a single spin of a 1D [Ising model](https://en.wikipedia.org/wiki/Ising_model).

The steps of the Metropolis-Hastings alogrithm are run on-chip, so no external random numbers or lookup tables are needed. 

All parameters, programming the environment (neighbour spins, coupling constants and temperature) are input through the 7 inputs, together with the clock.

More details on this particular implementation can be found in the accompanying paper (coming soon).

![](Overview.png)

## Inputs
|Pin|Name|Function                                           |
|--|-----|---------------------------------------------------|
|0 |CLK  |Clock Input                                        |
|1 |T0   |LSB of the 3-bit temperature value                 |
|2 |T1   |Second bit of the temperature                      |
|3 |T2   |MSB of the 3-bit temperature value                 |
|4 |N1   |The value of neighbour 1 (up or down)              |
|5 |N2   |The value of neighbour 2 (up or down)              |
|6 |J    |The sign of the NN coupling constant J (+ or -)    |
|7 |H    |The value of the external field coupling H (1 or 0)|

## Outputs
|Pin|Name|Function                     |
|--|-----|-----------------------------|
|0 |UP   |Indicates if the spin is UP  |
|1 |/    |                             |
|2 |/    |                             |
|3 |DOWN |Indicates if the spin is DOWN|
|4 |/    |                             |
|5 |/    |                             |
|6 |/    |                             |
|7 |/    |                             |



# What is Tiny Tapeout?

TinyTapeout is an educational project that aims to make it easier and cheaper than ever to get your digital designs manufactured on a real chip!

Go to https://tinytapeout.com for instructions!

## How to change the Wokwi project

Edit the [info.yaml](info.yaml) and change the wokwi_id to match your project.

## How to enable the GitHub actions to build the ASIC files

Please see the instructions for:

* [Enabling GitHub Actions](https://tinytapeout.com/faq/#when-i-commit-my-change-the-gds-action-isnt-running)
* [Enabling GitHub Pages](https://tinytapeout.com/faq/#my-github-action-is-failing-on-the-pages-part)

## How does it work?

When you edit the info.yaml to choose a different ID, the [GitHub Action](.github/workflows/gds.yaml) will fetch the digital netlist of your design from Wokwi.

After that, the action uses the open source ASIC tool called [OpenLane](https://www.zerotoasiccourse.com/terminology/openlane/) to build the files needed to fabricate an ASIC.

## Resources

* [FAQ](https://tinytapeout.com/faq/)
* [Digital design lessons](https://tinytapeout.com/digital_design/)
* [Join the community](https://discord.gg/rPK2nSjxy8)

## What next?

* Share your GDS on Twitter, tag it [#tinytapeout](https://twitter.com/hashtag/tinytapeout?src=hashtag_click) and [link me](https://twitter.com/matthewvenn)!
