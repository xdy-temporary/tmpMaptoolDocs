.. contents::
   :depth: 3
..

Token Size refers to the standard sizes defined for each Grid Type. The
sizes mostly apply to those tokens on the Token layer representing PCs
and NPCs but can be used on any token no matter the layer.

.. _sizes_and_scales:

Sizes and Scales
================

The Size is what is presented in the Size drop-down in the Edit Token
dialog or the Size sub-menu of the right-click contextual menu of a
token. Internally a scale factor is also applied and that factor is
shown in the tables below.

The valid sizes for each type of grid are documented below, where
**Medium** is always 1 full grid cell. The **Scale** is a multiplier for
the size of the image after configuring it to fit within the stated
footprint. For example, the size on a square grid occupies a 3x3 cell
area and the image is scaled (**1.0**) to exactly fit that area. But the
size on a hex grid is 3 hexes scaled down 10% (**0.9**) so as to keep
the image slightly within the border of the 3 cells. On Square Grids the
sizes follow the D&D standard.

.. raw:: html

   <table class="wikitable" border="1" style="border-collapse: collapse; float: left; margin-right: 2em">

.. raw:: html

   <tr style="background-color:#e0ddd5">

.. raw:: html

   <th>

Hex Grid

.. raw:: html

   </th>

.. raw:: html

   <th>

Scale

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|1/6}}

.. raw:: html

   </td>

.. raw:: html

   <td>

0.408

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|1/4}}

.. raw:: html

   </td>

.. raw:: html

   <td>

0.5

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|1/3}}

.. raw:: html

   </td>

.. raw:: html

   <td>

0.577

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|1/2}}

.. raw:: html

   </td>

.. raw:: html

   <td>

0.707

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|2/3}}

.. raw:: html

   </td>

.. raw:: html

   <td>

0.816

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Medium}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.0

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Large}}

.. raw:: html

   </td>

.. raw:: html

   <td>

0.9 (3 cells)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Huge}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.0 (7 cells)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Humongous}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.0 (19 cells)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

.. raw:: html

   <table class="wikitable" border="1" style="border-collapse: collapse">

.. raw:: html

   <tr style="background-color:#e0ddd5">

.. raw:: html

   <th>

Square Grid

.. raw:: html

   </th>

.. raw:: html

   <th>

Scale

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Fine}}

.. raw:: html

   <td>

0.5

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Diminutive}}

.. raw:: html

   <td>

0.5

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Tiny}}

.. raw:: html

   <td>

0.5

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Small}}

.. raw:: html

   <td>

0.75

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Medium}}

.. raw:: html

   <td>

1.0

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Large}}

.. raw:: html

   <td>

1.0 (2x2)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Huge}}

.. raw:: html

   <td>

1.0 (3x3)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Gargantuan}}

.. raw:: html

   <td>

1.0 (4x4)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|Colossal}}

.. raw:: html

   <td>

1.0 (6x6)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

| 

.. raw:: html

   <table class="wikitable" border="1" style="border-collapse: collapse; margin-top: 1em">

.. raw:: html

   <tr style="background-color:#e0ddd5">

.. raw:: html

   <th>

Gridless

.. raw:: html

   </th>

.. raw:: html

   <th>

Scale

.. raw:: html

   </th>

.. raw:: html

   <th>

Gridless

.. raw:: html

   </th>

.. raw:: html

   <th>

Scale

.. raw:: html

   </th>

.. raw:: html

   <th>

Gridless

.. raw:: html

   </th>

.. raw:: html

   <th>

Scale

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-11}}

.. raw:: html

   <td>

0.086

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|0}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.0

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|11}}

.. raw:: html

   <td>

7.43

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-10}}

.. raw:: html

   <td>

0.107

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|1}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.2

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|12}}

.. raw:: html

   <td>

8.916

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-9}}

.. raw:: html

   <td>

0.134

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|2}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.44

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|13}}

.. raw:: html

   <td>

10.699

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-8}}

.. raw:: html

   <td>

0.168

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|3}}

.. raw:: html

   </td>

.. raw:: html

   <td>

1.728

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|14}}

.. raw:: html

   <td>

12.839

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-7}}

.. raw:: html

   <td>

0.21

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|4}}

.. raw:: html

   </td>

.. raw:: html

   <td>

2.074

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|15}}

.. raw:: html

   <td>

15.407

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-6}}

.. raw:: html

   <td>

0.262

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|5}}

.. raw:: html

   </td>

.. raw:: html

   <td>

2.488

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|16}}

.. raw:: html

   <td>

18.488

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-5}}

.. raw:: html

   <td>

0.328

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|6}}

.. raw:: html

   </td>

.. raw:: html

   <td>

2.986

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|17}}

.. raw:: html

   <td>

22.186

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-4}}

.. raw:: html

   <td>

0.41

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|7}}

.. raw:: html

   </td>

.. raw:: html

   <td>

3.583

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|18}}

.. raw:: html

   <td>

26.623

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-3}}

.. raw:: html

   <td>

0.512

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|8}}

.. raw:: html

   </td>

.. raw:: html

   <td>

4.3

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|19}}

.. raw:: html

   <td>

31.948

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-2}}

.. raw:: html

   <td>

0.64

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|9}}

.. raw:: html

   </td>

.. raw:: html

   <td>

5.16

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|20}}

.. raw:: html

   <td>

38.338

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|-1}}

.. raw:: html

   <td>

0.8

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: mediawiki

   {{code|10}}

.. raw:: html

   </td>

.. raw:: html

   <td>

6.192

.. raw:: html

   </td>

.. raw:: html

   <td colspan="2">

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </table>

.. raw:: mediawiki

   {{Clarify|It would be nice to include pictures that demonstrate how the grid cells are composed; at least for the hex grids.}}

`Category:Token <Category:Token>`__
