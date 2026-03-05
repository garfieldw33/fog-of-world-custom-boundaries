# fog-of-world-custom-boundaries
Custom boundary snapshots for Fog of World, to help FoW users understand what truly counts toward region progress.

Currently included:  

| Code | Name | Number of blocks covered<sup>**1**</sup> | Maximum explorable area (*km<sup>2</sup>*) | Area required for 100% progress (*km<sup>2</sup>*)|
|------|------|:----:|------|------|
| [MAC](https://github.com/garfieldw33/fog-of-world-custom-boundaries/tree/main/Boundaries/MAC_Macau_SAR_China) | Macau SAR | 158 | 49.07 |30.3 |
| [MCO](https://github.com/garfieldw33/fog-of-world-custom-boundaries/tree/main/Boundaries/MCO_Monaco) | Monaco | 14 | 2.733 | 2.02  |
| [VAT](https://github.com/garfieldw33/fog-of-world-custom-boundaries/tree/main/Boundaries/VAT_Vantican_City) | Vatican City | 2  | 0.4143 | 0.44 (not achievable)  |

* <sup>1</sup>- A block is a 64*64-pixel box in FoW, each labeled with **one region**, and has explorable area of ~0.XX km<sup>2</sup> (depending on the latitude). 


Description:
* Under dir [/Boundaries](https://github.com/garfieldw33/fog-of-world-custom-boundaries/tree/main/Boundaries), files starting with...
	* "**B_XXX**": FoW **b**oundary lines around the region.
	* "**F_XXX**": Solid **f**illed FoW blocks counting towards the region.

## 🌍
This might be helpful for those Fog of World users who want to seek high percentage% in some small regions—such as Vatican City.

It's based on a fact that, FoW does not calculate region progress on real‑world boundaries. Instead, it relies on internal data/APIs to determine whether each pixel belongs to a region. This means the “true” region that counts toward your percentage, may be differently shaped than the real boundary.

I live in Macau, a Chinese city of only ~30 km^2. It took me like one hour to draw the boundary below through FoW's build-in editor. This is the smallest valid boundary I could identify for Macau in this App, any single dot inside this frame counts as Macau.

<img width="225" height="488" alt="MAC" src="https://github.com/user-attachments/assets/de1b2564-9b3b-4d24-a745-f4b9f69cfcaf" />



To see if it works, I erased all pixels outside the frame from my original data. Reveals the two both produced identical values for area of Macau.

<img width="451" height="488" alt="macau_verify" src="https://github.com/user-attachments/assets/098d27c3-76aa-4b38-b412-278c9e1a6ab6" />


To make it fun, i also mapped out the FoW boundary of Vatican. On my side, every pixels inside the rectangle (in the pic below) contributes to achievement & percentage related to Vatican City, while all those on or outside the box do not. even if some of them fall within the real‑world Vatican boundary.

<img width="225" height="488" alt="VAT" src="https://github.com/user-attachments/assets/a0fe24e1-58fd-4fc9-8d61-d2f05c0cd29b" />


## How to use these Snapshots?

You may place the snapshots in this repo (under dir [/Boundaries](https://github.com/garfieldw33/fog-of-world-custom-boundaries/tree/main/Boundaries)) into your FoW database. So the next time you visit Vatican City and really want to maximize your percentage, you'll know exactly which corners to go.

<img width="451" height="488" alt="mapref" src="https://github.com/user-attachments/assets/10e277a8-4ad3-4bf1-b384-2c1730259078" />

The correctness of the boundaries is not guaranteed. You are also welcomed to contribute the repo with updated data if any, or draw boundaries for more regions.

***
## -
* The snapshots were verified on FoW version 3.7.3 (1461).

* Polished using [v佬](https://fog.vicc.wang)'s toolbox on [https://fog.vicc.wang].
