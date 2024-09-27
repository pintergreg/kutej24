---
title: Az úthálózat összekötő és elválasztó hatása
author: Pintér Gergő^1^ és Lengyel Balázs^1,2,3^
date: "2024. szeptember 27."
institute: >-
    ^1^ANETI Lab, Budapesti Corvinus Egyetem<br>
    ^2^ANETI Lab, HUN-REN Közgazdaság- és Regionális Tudományi Kutatóközpont<br>
    ^3^Adatelemzés és Informatika Intézet, Budapesti Corvinus Egyetem

title-slide-attributes:
    data-background-color: "#181d37"
    data-background-image: assets/corvinus_and_aneti.svg
    data-background-size: 23vw
    data-background-position: 1.25rem calc(100% - 1.25rem)
slideNumber: "true"
showSlideNumber: "print"
revealjs-url: "assets/reveal.js-5.1.0/"
---

# motiváció

:::::::::::::: {.columns}
::::::::: {.column width="30%"}
:::::: {.r-stack}
::: {}
![](figures/route_connect.png)
:::
::: {.fragment data-fragment-index=1}
![](figures/route_connect_and_divide_marker.png)
:::
::::::
:::::::::
::::::::: {.column width="80%"}
::: {.fragment data-fragment-index=1}
![Nagykőrösi út (Budapest)<br/>[vst](https://www.mapillary.com/app/user/vst), [Mapillary](https://www.mapillary.com/app/?lat=47.45252492224&lng=19.11784766168&z=17&pKey=1294650608077501&focus=photo) [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)](figures/vst_1294650608077501_20230915_cropped.jpg)
:::
:::::::::
::::::::::::::


# hely adatok telefonos alkalmazásokból

:::::::::::::: {.columns}
::: {.column width="55%"}
![](figures/pings_stops.png){height=375}

:::
::: {.column width="45%" .text-smallerx .mt-3}
- különböző okostelefon alkalmazásokból összegyűjtve
    - időpont, azonosító, hely
    - GPS koordináta
- felbukkanásokat térben és időben csoportosítjuk
    - olyan helyeket keresünk, ahol egy felhasználó eltöltött valamennyi időt
:::
::::::::::::::


## építsünk hálózatot

:::::::::::::: {.columns}
::: {.column width="50%"}
![tekintsük háztömböket a hálózat csúcsainak](figures/stops_to_blocks.png)
:::
::: {.column width="50%"}
![amelyeket összekötünk ha valaki egymás után felbukkan két háztömbben egy napon belül](figures/blocks_network_real_pos.png)
:::
::::::::::::::


# közösség elemzés

:::::::::::::: {.columns}
:::::: {.column .center-content width="50%"}
![](figures/community.png)

::::::
:::::: {.column width="50%" .fragment}
![Louvain közösségek<br/>(felbontás: 2.5)](figures/network_v2.png)

::::::
::::::::::::::


## közlekedési közösségek

:::::::::::::: {.columns}
:::::: {.column width="40%"}
![magasabb rendű utakkal összehasonlítva](figures/louvain_resolution2.5_two_level_barriers.png)
::::::
:::::: {.column width="40%" .fragment}
![kerületekkel összevetve](figures/louvain_resolution2.5_two_level_districts.png)
::::::
::::::::::::::


## akadályok dinamikája

:::::::::::::: {.columns .column-gapless}
:::::: {.column width="20%"}
![](figures/d15_r2.5.svg)
::::::
:::::: {.column width="20%" .fragment}
![](figures/d15_r4.0.svg)
::::::
:::::: {.column width="20%" .fragment}
![](figures/d15_r6.0.svg)
::::::
:::::: {.column width="20%" .fragment}
![](figures/d15_r6.5.svg)
::::::
:::::: {.column width="20%" .fragment}
![](figures/d15_r8.0.svg)
::::::
::::::::::::::


# akadályátlépések

::::::::::::::: {.columns}
:::::::::::: {.column width="50%"}
::::::::: {.r-stack}
:::::: {}
![](figures/barrier_and_community_crossing_1.png)
::::::
:::::: {.fragment data-fragment-index=1}
![](figures/barrier_and_community_crossing_2.png)
::::::
:::::: {.fragment data-fragment-index=2}
![](figures/barrier_and_community_crossing_3.png)
::::::
:::::::::
::::::::::::
:::::::::::: {.column width="50%"}
::::::::: {.r-stack}
:::::: {.fragment data-fragment-index=7 .current-visible}
típusonként összesítjük:

::: {.text-smaller}
- kerület
- városrész
- magasabb rendű utak
- alacsonyabb rendű utak
- vasút
- folyó
:::
::::::
:::::::::
::::::::::::
:::::::::::::::


## miképp hat mindez az emberekre?

csak a Budapesten belüli mozgásokat vesszük figyelembe

::: {.fragment data-fragment-index=3}
azonban a szétválasztjuk a budapesti lakosokat az agglomerációban élőktől
:::

:::::: {.r-stack}
::: { .mt-5 .current-visible}
![](figures/trips.drawio.png){width=400}
:::
::: {.fragment data-fragment-index=3 .mt-5 .current-visible}
![](figures/trips_and_homes.drawio.png){width=400}
:::
::::::

# tegyük egybe az egészet

:::::::::::::: {.columns}
:::::: {.column width="33%"}
![közösségképzés](figures/community.png)

::::::
:::::: {.column width="33%"}
![akadályátlépések](figures/barrier_and_community_crossing_3.png)

::::::
:::::: {.column width="33%"}
![ki hol lakik](figures/trips_and_homes_square.drawio.png)

::::::
::::::::::::::

## úthálózat akadályozó hatása lakhely alapján

:::::::::::::: {.columns}
:::::: {.column width="30%"}
![](figures/map_with_legend_diverging.png)

::::::
:::::: {.column width="70%" .fragment}
![](figures/bcr_orig_comm_diverging.png)

::::::
::::::::::::::


# köszönöm a figyelemet! {background-color="#181d37" .text-color-white background-image="assets/by-sa.svg" background-size="10vw" background-position="1.25rem calc(100% - 1.25rem)" .light-slide-number}

::: {.text-color-white}
Pintér Gergő<br><span class="text-color-lightblue">gergo.pinter&ThinSpace;&#64;&ThinSpace;uni-corvinus.hu</span>
:::


## szolgáltatások színre lépnek {visibility="hidden"}

:::::::::::::: {.columns}
::::::::: {.column width="50%"}
:::::: {.r-stack}
::: {}
![](figures/amenity_attracts.png){width=350}

:::
::::::
:::::::::
::::::::: {.column width="50%" .mt-5}
- speciális szolgáltatások jelentősen befolyásolják a mobilitás irányát
- és „csökkentik” az akadály hatást

:::::::::
::::::::::::::


# úthálózat akadályozó hatása lakhely alapján 2 {visibility=uncounted}

:::::::::::::: {.columns}
:::::: {.column width="30%"}
![](figures/map_with_legend.png)

::::::
:::::: {.column width="70%"}
![](figures/bcr_orig_comm.png)

::::::
::::::::::::::
