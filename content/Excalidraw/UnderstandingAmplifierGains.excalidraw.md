---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
Input
Match ^QY1IJtZo

Output
Match ^KVkeMEtq

Device

[S] ^V119N2Vj

Input
Match ^17dq725i

Device

[S] ^8OozT7x7

Output
Match ^61i4SK9s

Fig 1 ^UvlqrKw9

Fig 2 ^JPzitV15

- (1) ^xSNtEIVG

- (2) ^ULgGOnr3

- (3) ^qA4bdYzr

- (4) ^AL1T71QR

Z0 ^vZEnSwOy

Z0 ^EE5UW73h

Vs ^WtDWjUYA

Z0 ^01GB7vzA

Z0 ^87YV8cjk

Vs ^gwCsFVZ8

Input
Match ^ZvRZuBJw

Device

[S] ^lv1ex2xW

Output
Match ^5QYF4Cgn

Fig 3 ^QPKOBAHj

Z0 ^vEHOG2Lv

Z0 ^rJDjnpXB

Vs ^5susUU3d

Power available
from source (Pavs) ^kKx8OD8M

Power delivered
to the input (Pin) ^MZQoFuBl

Power available
from the network (Pavn) ^GrKUB8x4

Power delivered
to the load (PL) ^9G3lNOd3

Input
Match ^cFcuYJbG

Device

[S] ^3QgVMamb

Output
Match ^qfDlzDFa

Fig 4 ^DDZFW22V

Z0 ^TC1oIKKx

Z0 ^u5cgdFOF

Vs ^JkSlILXK

Power available
from source (Pavs) ^k95tgMP9

Power delivered
to the load (PL) ^eaoWb20V

Transducer Gain ^X3Lz3LFI

Input
Match ^LQvFSWJ1

Device

[S] ^YSx0huv2

Output
Match ^3YiJSVqY

Z0 ^fIFR4eoI

Z0 ^OIWtXDYQ

Vs ^yTu04cRP

Power delivered
to the input (Pin) ^0KQqi1bu

Power delivered
to the load (PL) ^OMoOXOgk

Fig 5 ^rwx30Frf

Power Gain ^4qMdQujm

Input
Match ^uETzzINZ

Device

[S] ^wpSg3arN

Output
Match ^dnEMPRIS

Z0 ^Rnmo0jz3

Z0 ^EsROzqvF

Vs ^XWNyCIXl

Power available
from source (Pavs) ^9y2bg1lL

Power available
from the network (Pavn) ^sR2Ps12v

Fig 6 ^mAS9qyZn

Available Gain ^uqsoWSNw

- (5) ^6WQyJZzB

GS ^lCUtWMo4

GL ^cWolS16g

GT0 ^WFbqY3JH

GS ^V3PLkYyn

GT0 ^1hibNwpP

GL ^v1ZIQ5kO

- (6) ^NTqethFo

- (7) ^k52wP6T5

- (8) ^eHYvI7Qy

- (9) ^QWe20b6b


# Embedded files
bc8ef0a2142ac059b4d7815ba06a6db5baa6e654: $$Z_S (\Gamma_S)$$
a857754597ce55d7dacb8d7e901a986ce306470f: $$Z_L (\Gamma_L)$$
594d60eca65cfdd25f8dbd74ba4fe505e1b579f8: $$Z_{in} (\Gamma_{in})$$
e3ce8771838aac1a26fcec5f359895e7482e7252: $$Z_{out} (\Gamma_{out})$$
9b4c36b85f842a0e1ca75ed557ce9f22ac33b518: $$\Gamma_S = \frac{Z_S-Z_0}{Z_S+Z_0}$$
c1317362466c27fc57f090149626094b272ec668: $$\Gamma_L = \frac{Z_L-Z_0}{Z_L+Z_0}$$
81bda6bb29cd637ac890ce96a5d2bd6589e1bba6: $$\Gamma_{in} = S_{11} + \frac{S_{12}S_{21}\Gamma_L}{1-S_{22}\Gamma_L}$$
ff598ec145151388c611a8e2e5b24e21cfdffb7f: $$\Gamma_{out} = S_{22} + \frac{S_{12}S_{21}\Gamma_S}{1-S_{11}\Gamma_S}$$
6bc4b548241eef3f8aab8900f6b04d3dc1d66377: $$Z_S (\Gamma_S)$$
d4bf9232f310046a402d644884d8957ff3774dce: $$Z_L (\Gamma_L)$$
61e294deb146f54b67ff85dc6568c861c8345551: $$Z_{in} (\Gamma_{in})$$
9c3d557e88d3610e2a4e94f9dc6c4ee36681f5ac: $$Z_{out} (\Gamma_{out})$$
875c3c4d7b7700947bb434dbeb28505f91081755: $$G_T = \frac{P_L}{P_{avs}} = \frac{|S_{21}|^2 (1-|\Gamma_S|^2) (1-|\Gamma_L|^2)}{|1-\Gamma_S\Gamma_{in}|^2 |1-S_{22}\Gamma_L|^2}$$
1cd270cde818361ea5d83eb0490ad529bd05c1f6: $$G_T = \frac{P_L}{P_{avs}} = \frac{1-|\Gamma_S|^2}{|1-S_{11}\Gamma_S\|^2} \times |S_{21}|^2 \times \frac{1-|\Gamma_L|^2}{|1-S_{22}\Gamma_L|^2}$$
0fa511a2e86334c53716c287214466250bec1d34: $$G_{T0} = |S_{21}|^2$$
06dd33beaf2ab62353615936cf4d9d3be53d0cbc: $$G_P = \frac{P_L}{P_{in}} = \frac{|S_{21}|^2 (1-|\Gamma_L|^2)}{(1-|\Gamma_{in}|^2) |1-S_{22}\Gamma_L|^2}$$
d390a398e4795073916b6ce5c33fb40ad5c7f410: $$G_A = \frac{P_{avn}}{P_{avs}} = \frac{|S_{21}|^2 (1-|\Gamma_S|^2)}{|1-S_{11}\Gamma_S\|^2 (1-|\Gamma_{out}|^2)}$$

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.16",
	"elements": [
		{
			"type": "rectangle",
			"version": 1137,
			"versionNonce": 55354285,
			"isDeleted": false,
			"id": "yA4IAfjQq97YykS6w6UlW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -267.8774503381819,
			"y": 1994.1791354272666,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e6fcf5",
			"width": 433.50374279315616,
			"height": 181.70509131379552,
			"seed": 1416520323,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "bUFCcvfbJqHGBuoXXctiX",
					"type": "arrow"
				}
			],
			"updated": 1704981547723,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 782,
			"versionNonce": 852992899,
			"isDeleted": false,
			"id": "6l0Uft3sYyMUngjZd7q00",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -58.81094135351816,
			"y": 1383.7607335699174,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e6fcf5",
			"width": 433.50374279315616,
			"height": 181.70509131379552,
			"seed": 354710893,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PdlkrnZZ7i6y8eZpmt4Sp",
					"type": "arrow"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 436,
			"versionNonce": 929822019,
			"isDeleted": false,
			"id": "byU8f6LszLN2YiyY4MxFI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -210.9144797631784,
			"y": 707.2721356106659,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#e6fcf5",
			"width": 632.5558261264895,
			"height": 181.70509131379552,
			"seed": 692728589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "FxbMFe2_aV5JwmWpJH2pj",
					"type": "arrow"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "rectangle",
			"version": 415,
			"versionNonce": 1030435949,
			"isDeleted": false,
			"id": "QxVKPwHH2AQew9i2ED_mt",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.41796875,
			"y": -350.69140625,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 1227825337,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "QY1IJtZo"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 57,
			"versionNonce": 157439203,
			"isDeleted": false,
			"id": "QY1IJtZo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -117.30912017822266,
			"y": -326.326171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.87995910644531,
			"height": 50,
			"seed": 1017510531,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Input\nMatch",
			"rawText": "Input\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "QxVKPwHH2AQew9i2ED_mt",
			"originalText": "Input\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 619,
			"versionNonce": 1950621389,
			"isDeleted": false,
			"id": "LVjSvQbQVnlB9KWVGe0My",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 82.017578125,
			"y": -369.283203125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 102.09765625,
			"height": 130.16015625,
			"seed": 1034958295,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "V119N2Vj"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 74,
			"versionNonce": 2024521859,
			"isDeleted": false,
			"id": "V119N2Vj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 101.88643646240234,
			"y": -341.703125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.35993957519531,
			"height": 75,
			"seed": 1861621453,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Device\n\n[S]",
			"rawText": "Device\n\n[S]",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "LVjSvQbQVnlB9KWVGe0My",
			"originalText": "Device\n\n[S]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 500,
			"versionNonce": 156286253,
			"isDeleted": false,
			"id": "VeMgSRscE_tmkrbG-HCsR",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 303.154296875,
			"y": -350.185546875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 383897241,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "KVkeMEtq"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 52,
			"versionNonce": 2131146787,
			"isDeleted": false,
			"id": "KVkeMEtq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 319.35316467285156,
			"y": -325.8203125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.69992065429688,
			"height": 50,
			"seed": 328527277,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Output\nMatch",
			"rawText": "Output\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "VeMgSRscE_tmkrbG-HCsR",
			"originalText": "Output\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 128,
			"versionNonce": 1677365133,
			"isDeleted": false,
			"id": "W4KGeVMJIhM5YVFoRLwCF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -34.76171875,
			"y": -303.26171875,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.00390625,
			"height": 0,
			"seed": 2065921687,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					117.00390625,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 113,
			"versionNonce": 1516354499,
			"isDeleted": false,
			"id": "Sd4_KvNayLE2g3udTCQh8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 186.375,
			"y": -303.03125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.20703125,
			"height": 0,
			"seed": 258484311,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.20703125,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 144,
			"versionNonce": 1115362797,
			"isDeleted": false,
			"id": "CDX4HLohxN72Gp8rbG5nd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -139.05859375,
			"y": -302.26953125,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.411876592399835,
			"height": 0,
			"seed": 251631833,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-40.411876592399835,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 180,
			"versionNonce": 115034979,
			"isDeleted": false,
			"id": "D8whrPF_Lc7PFVVkk_Fy1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 464.63835026105863,
			"y": -302.06719129121865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.484375,
			"height": 0,
			"seed": 10544121,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-58.484375,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 566,
			"versionNonce": 1608241229,
			"isDeleted": false,
			"id": "8cTSNW_ynQ367djLiqxpD",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -174.17019687748666,
			"y": -303.0100830094196,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 152934775,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "line",
			"version": 729,
			"versionNonce": 2025973507,
			"isDeleted": false,
			"id": "cOWcsuPbNbsSZckxkaq8Q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": 504.35354491355974,
			"y": -264.54746185407254,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 1406273507,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "ellipse",
			"version": 201,
			"versionNonce": 1509310125,
			"isDeleted": false,
			"id": "rdf-2z02E7DHHNmR_D1f1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -263.6957074882099,
			"y": -264.65638099240584,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.590205478603195,
			"height": 29.590205478603195,
			"seed": 1287084355,
			"groupIds": [
				"gLY10luIg7ECnetY73WZ8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 478,
			"versionNonce": 378801827,
			"isDeleted": false,
			"id": "O_bXglqnyuu37VbBvJLo1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -256.7313700082756,
			"y": -248.72609913974335,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.62671951107037,
			"height": 13.263085679569341,
			"seed": 1635946947,
			"groupIds": [
				"gLY10luIg7ECnetY73WZ8"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.395035361670153,
					-8.19912256579595
				],
				[
					12.787279608307504,
					5.063963113773392
				],
				[
					16.62671951107037,
					-2.3521404937578243
				]
			]
		},
		{
			"type": "line",
			"version": 87,
			"versionNonce": 1467212045,
			"isDeleted": false,
			"id": "OoRcQQU3yx61sWAS11Cq0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -249.7780447123569,
			"y": -302.70659378504104,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1292332013,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 155,
			"versionNonce": 1929396803,
			"isDeleted": false,
			"id": "3gsWYo3Svb8ob-7ayLuGV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -248.4143787012745,
			"y": -234.90813856630913,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1025916195,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 152,
			"versionNonce": 1842231149,
			"isDeleted": false,
			"id": "u_bjS_2CKLzPGse39pCtw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -255.68590335643336,
			"y": -195.92050333857793,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 867577571,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 232,
			"versionNonce": 1189413347,
			"isDeleted": false,
			"id": "styXotf9R1uUZlJXXTKQa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 457.7196404698543,
			"y": -202.4182620183148,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 1146655299,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 88,
			"versionNonce": 1196343757,
			"isDeleted": false,
			"id": "9s1MvVfgEZu8QLByK62EN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 466.52907565235876,
			"y": -226.5589078092501,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 22.603366534780093,
			"seed": 42534573,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					22.603366534780093
				]
			]
		},
		{
			"type": "rectangle",
			"version": 481,
			"versionNonce": 726715779,
			"isDeleted": false,
			"id": "x3Oq0hpdHAhNSsmj2NUat",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -148.67409279890097,
			"y": -64.24975029606344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 1394274573,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "17dq725i"
				},
				{
					"id": "M350p47giAQ4QHZx2p-Zb",
					"type": "arrow"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 122,
			"versionNonce": 151978029,
			"isDeleted": false,
			"id": "17dq725i",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -127.56524422712363,
			"y": -39.88451592106344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.87995910644531,
			"height": 50,
			"seed": 34817901,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Input\nMatch",
			"rawText": "Input\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "x3Oq0hpdHAhNSsmj2NUat",
			"originalText": "Input\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 686,
			"versionNonce": 327296291,
			"isDeleted": false,
			"id": "vPJS9Wzw1YpZm2nlcZeej",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 71.76145407609903,
			"y": -82.84154717106344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 102.09765625,
			"height": 130.16015625,
			"seed": 812765645,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "8OozT7x7"
				},
				{
					"id": "g8MWAsu_LBciutYxdFxy7",
					"type": "arrow"
				},
				{
					"id": "gO0NHMSn_c3p-bTzZ2MGf",
					"type": "arrow"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 139,
			"versionNonce": 2029548173,
			"isDeleted": false,
			"id": "8OozT7x7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 91.63031241350137,
			"y": -55.26146904606344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.35993957519531,
			"height": 75,
			"seed": 2068844589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Device\n\n[S]",
			"rawText": "Device\n\n[S]",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "vPJS9Wzw1YpZm2nlcZeej",
			"originalText": "Device\n\n[S]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 566,
			"versionNonce": 115837123,
			"isDeleted": false,
			"id": "-FxcO3UKM_zmj3aMjFxMm",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 292.898172826099,
			"y": -63.74389092106344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 546800269,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "61i4SK9s"
				},
				{
					"id": "ZQ9JmzFkDDF05bn7G9-4G",
					"type": "arrow"
				}
			],
			"updated": 1704980729353,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 117,
			"versionNonce": 1673828589,
			"isDeleted": false,
			"id": "61i4SK9s",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 309.0970406239506,
			"y": -39.37865654606344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.69992065429688,
			"height": 50,
			"seed": 1694607597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Output\nMatch",
			"rawText": "Output\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "-FxcO3UKM_zmj3aMjFxMm",
			"originalText": "Output\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 193,
			"versionNonce": 455047267,
			"isDeleted": false,
			"id": "WlHdHC7YlIDRZZQOh6MkA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -45.01784279890097,
			"y": -16.82006279606344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.00390625,
			"height": 0,
			"seed": 974652237,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					117.00390625,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 178,
			"versionNonce": 1123873613,
			"isDeleted": false,
			"id": "oMUDNL3UWwUZ9-2lZmuFi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 176.11887595109903,
			"y": -16.58959404606344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.20703125,
			"height": 0,
			"seed": 607392173,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.20703125,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 209,
			"versionNonce": 771257347,
			"isDeleted": false,
			"id": "9mn-O1ttrEpKOaBpIFlUK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -149.31471779890097,
			"y": -15.82787529606344,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.411876592399835,
			"height": 0,
			"seed": 1618957325,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729353,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-40.411876592399835,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 245,
			"versionNonce": 586875309,
			"isDeleted": false,
			"id": "34kM8lY3msWq4rKNB_NWc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 454.38222621215766,
			"y": -15.625535337282088,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 58.484375,
			"height": 0,
			"seed": 1257458285,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-58.484375,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 631,
			"versionNonce": 1601239971,
			"isDeleted": false,
			"id": "4LQ3RBnqLSDpM8w2EfTLg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -184.42632092638763,
			"y": -16.568427055483028,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 72971469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "line",
			"version": 794,
			"versionNonce": 1223181325,
			"isDeleted": false,
			"id": "hF9RPG6UAoyG9nxtdME9K",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": 494.0974208646588,
			"y": 21.894194099864023,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 1481331501,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "ellipse",
			"version": 266,
			"versionNonce": 1270320963,
			"isDeleted": false,
			"id": "Rh4W5pnQtGzA40gHDW4qh",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -273.95183153711093,
			"y": 21.785274961530718,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.590205478603195,
			"height": 29.590205478603195,
			"seed": 1664247181,
			"groupIds": [
				"BBPMThYfziqP7Xm6u8aQm"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 543,
			"versionNonce": 415119981,
			"isDeleted": false,
			"id": "T1MqytDBxrGBuFkznuBiV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -266.9874940571766,
			"y": 37.715556814193235,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.62671951107037,
			"height": 13.263085679569341,
			"seed": 2017995757,
			"groupIds": [
				"BBPMThYfziqP7Xm6u8aQm"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.395035361670153,
					-8.19912256579595
				],
				[
					12.787279608307504,
					5.063963113773392
				],
				[
					16.62671951107037,
					-2.3521404937578243
				]
			]
		},
		{
			"type": "line",
			"version": 152,
			"versionNonce": 86683363,
			"isDeleted": false,
			"id": "rKfccmYu7uLs1nApabiC3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -260.0341687612579,
			"y": -16.264937831104476,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1201022541,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 220,
			"versionNonce": 994469069,
			"isDeleted": false,
			"id": "qIrT-SQv7IfftEUxQif0q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -258.6705027501755,
			"y": 51.533517387627455,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1140184237,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 217,
			"versionNonce": 1314445955,
			"isDeleted": false,
			"id": "Chld08a6DnQMJlsllWRfO",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -265.94202740533433,
			"y": 90.52115261535863,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 1225832205,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 297,
			"versionNonce": 68829997,
			"isDeleted": false,
			"id": "glypl-Cx3wI-OUQJmkvAF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 447.46351642095334,
			"y": 84.02339393562175,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 23088493,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 153,
			"versionNonce": 335581731,
			"isDeleted": false,
			"id": "8qxGMymF4sifYZgNnU77G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 456.2729516034578,
			"y": 59.8827481446865,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 22.603366534780093,
			"seed": 204347341,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					22.603366534780093
				]
			]
		},
		{
			"type": "arrow",
			"version": 367,
			"versionNonce": 235429613,
			"isDeleted": false,
			"id": "M350p47giAQ4QHZx2p-Zb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -17.819131541875272,
			"y": 75.29307094540111,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.510874808381402,
			"height": 65.93186640283365,
			"seed": 99251587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129302,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "jJOAJ8eq",
				"focus": 0.17730239781981103,
				"gap": 15.950352908443776
			},
			"endBinding": {
				"elementId": "x3Oq0hpdHAhNSsmj2NUat",
				"gap": 3.8073780766538903,
				"focus": 0.5647772607160223
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.5609478780095944,
					-65.93186640283365
				],
				[
					-24.94992693037181,
					-64.13267503207864
				]
			]
		},
		{
			"type": "arrow",
			"version": 453,
			"versionNonce": 1020787021,
			"isDeleted": false,
			"id": "g8MWAsu_LBciutYxdFxy7",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 44.98443742781084,
			"y": 87.21208220443818,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 25.98860502274326,
			"height": 75.32365604633647,
			"seed": 953762413,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129302,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "4R2dvrQk",
				"focus": -0.1551900952280648,
				"gap": 6.245165431152216
			},
			"endBinding": {
				"elementId": "vPJS9Wzw1YpZm2nlcZeej",
				"gap": 3.4709705661711467,
				"focus": -0.5143808425574228
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-2.682558940626218,
					-75.32365604633647
				],
				[
					23.306046082117042,
					-73.49077206073837
				]
			]
		},
		{
			"type": "arrow",
			"version": 319,
			"versionNonce": 2005223341,
			"isDeleted": false,
			"id": "gO0NHMSn_c3p-bTzZ2MGf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 200.66054521163522,
			"y": 88.92615978560119,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 25.510874808381402,
			"height": 74.22621421050621,
			"seed": 558139533,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129302,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "0zFnzl7A",
				"focus": 0.18291834867308987,
				"gap": 6.987030855366044
			},
			"endBinding": {
				"elementId": "vPJS9Wzw1YpZm2nlcZeej",
				"gap": 3.925546020849083,
				"focus": 0.5552933532033113
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					2.6349859436942893,
					-74.22621421050621
				],
				[
					-22.875888864687113,
					-72.42702283975122
				]
			]
		},
		{
			"type": "arrow",
			"version": 513,
			"versionNonce": 1614400013,
			"isDeleted": false,
			"id": "ZQ9JmzFkDDF05bn7G9-4G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 266.25282602024834,
			"y": 89.02087153863084,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.98860502274326,
			"height": 75.61621378881954,
			"seed": 371060461,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129302,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "X7Vgfhm6",
				"focus": -0.09378688749997408,
				"gap": 8.647156324455466
			},
			"endBinding": {
				"elementId": "-FxcO3UKM_zmj3aMjFxMm",
				"gap": 3.341071875490343,
				"focus": -0.6315829688167252
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-2.6843300923829103,
					-75.61621378881954
				],
				[
					23.30427493036035,
					-73.78332980322145
				]
			]
		},
		{
			"type": "image",
			"version": 171,
			"versionNonce": 1753945677,
			"isDeleted": false,
			"id": "jJOAJ8eq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -48.056180029412985,
			"y": 91.24342385384489,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51,
			"height": 16,
			"seed": 17728,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "M350p47giAQ4QHZx2p-Zb",
					"type": "arrow"
				}
			],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "bc8ef0a2142ac059b4d7815ba06a6db5baa6e654",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 217,
			"versionNonce": 168952067,
			"isDeleted": false,
			"id": "X7Vgfhm6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 243.3088841530352,
			"y": 97.66802786308631,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 52,
			"height": 16,
			"seed": 37445,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ZQ9JmzFkDDF05bn7G9-4G",
					"type": "arrow"
				}
			],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "a857754597ce55d7dacb8d7e901a986ce306470f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 82,
			"versionNonce": 1489814701,
			"isDeleted": false,
			"id": "4R2dvrQk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 21.036489382929688,
			"y": 93.45724763559039,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 58,
			"height": 16,
			"seed": 34915,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "g8MWAsu_LBciutYxdFxy7",
					"type": "arrow"
				}
			],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "594d60eca65cfdd25f8dbd74ba4fe505e1b579f8",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 105,
			"versionNonce": 2060511395,
			"isDeleted": false,
			"id": "0zFnzl7A",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 159.2658836739658,
			"y": 95.91319064096723,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 69,
			"height": 16,
			"seed": 26326,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "gO0NHMSn_c3p-bTzZ2MGf",
					"type": "arrow"
				}
			],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "e3ce8771838aac1a26fcec5f359895e7482e7252",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 119,
			"versionNonce": 92907277,
			"isDeleted": false,
			"id": "UvlqrKw9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 92.85430071450679,
			"y": -198.23846165464838,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 33.03997802734375,
			"height": 20,
			"seed": 1492344643,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fig 1",
			"rawText": "Fig 1",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fig 1",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 191,
			"versionNonce": 781311043,
			"isDeleted": false,
			"id": "JPzitV15",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 98.74280517795944,
			"y": 135.090645622277,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.095977783203125,
			"height": 20,
			"seed": 657722541,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fig 2",
			"rawText": "Fig 2",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fig 2",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 123,
			"versionNonce": 557530477,
			"isDeleted": false,
			"id": "598uDOrC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -252.63376280293295,
			"y": 217.80863133035723,
			"strokeColor": "#000000",
			"backgroundColor": "#ffffff",
			"width": 106,
			"height": 36,
			"seed": 51339,
			"groupIds": [
				"ewDloZ9w-CircyEUDjoNQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9b4c36b85f842a0e1ca75ed557ce9f22ac33b518",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 106,
			"versionNonce": 288578531,
			"isDeleted": false,
			"id": "xSNtEIVG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -101.51452105716197,
			"y": 226.08965114060948,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 30.959976196289062,
			"height": 20,
			"seed": 1097587469,
			"groupIds": [
				"ewDloZ9w-CircyEUDjoNQ"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (1)",
			"rawText": "- (1)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (1)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 186,
			"versionNonce": 1395328973,
			"isDeleted": false,
			"id": "uCfjCP8A",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -251.38735558748988,
			"y": 286.3187924336831,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 106,
			"height": 36,
			"seed": 46633,
			"groupIds": [
				"WOBc6BuMYP3octbqrDw3q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "c1317362466c27fc57f090149626094b272ec668",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 215,
			"versionNonce": 247719811,
			"isDeleted": false,
			"id": "ULgGOnr3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -105.0137246801034,
			"y": 295.2363528255802,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.01597595214844,
			"height": 20,
			"seed": 1680544355,
			"groupIds": [
				"WOBc6BuMYP3octbqrDw3q"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (2)",
			"rawText": "- (2)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (2)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 111,
			"versionNonce": 494044717,
			"isDeleted": false,
			"id": "dGQEHTg5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 38.47724204187489,
			"y": 218.38979521237724,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 164,
			"height": 36,
			"seed": 62732,
			"groupIds": [
				"LvmP8AD6j1CQmry_lFtT1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "81bda6bb29cd637ac890ce96a5d2bd6589e1bba6",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 113,
			"versionNonce": 226623267,
			"isDeleted": false,
			"id": "qA4bdYzr",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 232.5463610865874,
			"y": 226.90988449809151,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 37.51997375488281,
			"height": 20,
			"seed": 2028010413,
			"groupIds": [
				"WOJADuL-WwXc_2wAtcS_R",
				"LvmP8AD6j1CQmry_lFtT1"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (3)",
			"rawText": "- (3)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (3)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 121,
			"versionNonce": 50018445,
			"isDeleted": false,
			"id": "zjQcMBZ2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 33.93536443680824,
			"y": 289.9859964347126,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 169,
			"height": 36,
			"seed": 82768,
			"groupIds": [
				"okXBowVndImlUdMX3k2Hq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "ff598ec145151388c611a8e2e5b24e21cfdffb7f",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 177,
			"versionNonce": 668738243,
			"isDeleted": false,
			"id": "AL1T71QR",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 233.04144898793828,
			"y": 297.2717107204269,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 36.86396789550781,
			"height": 20,
			"seed": 510620493,
			"groupIds": [
				"QhucGla-AQBl1RvklYJV7",
				"okXBowVndImlUdMX3k2Hq"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (4)",
			"rawText": "- (4)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (4)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 72,
			"versionNonce": 1837014765,
			"isDeleted": false,
			"id": "vZEnSwOy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -223.9915079581252,
			"y": -336.0867672876227,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 1773824173,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 116,
			"versionNonce": 644928099,
			"isDeleted": false,
			"id": "EE5UW73h",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 482.6954590741712,
			"y": -273.9773922876228,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 1469079203,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 197,
			"versionNonce": 1401305421,
			"isDeleted": false,
			"id": "WtDWjUYA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -228.4407016401146,
			"y": -260.5979280019085,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.959976196289062,
			"height": 20,
			"seed": 1880042499,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vs",
			"rawText": "Vs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vs",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 204,
			"versionNonce": 974032387,
			"isDeleted": false,
			"id": "01GB7vzA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -232.83414188669656,
			"y": -50.78668358226571,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 85681699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 247,
			"versionNonce": 510363565,
			"isDeleted": false,
			"id": "87YV8cjk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 471.47112871702836,
			"y": 13.673137846305622,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 1437641155,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 328,
			"versionNonce": 1974719907,
			"isDeleted": false,
			"id": "gwCsFVZ8",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -239.66503199725747,
			"y": 27.052602132019956,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.959976196289062,
			"height": 20,
			"seed": 1444706659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vs",
			"rawText": "Vs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vs",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 641,
			"versionNonce": 1347947021,
			"isDeleted": false,
			"id": "k0nVlyEKKpEzQMfE4or-W",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -159.1152166983921,
			"y": 415.2894607870794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 775770051,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "ZvRZuBJw"
				},
				{
					"id": "Wz-4_AoMj78D5VhyDzzhi",
					"type": "arrow"
				}
			],
			"updated": 1704980729354,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 280,
			"versionNonce": 143599939,
			"isDeleted": false,
			"id": "ZvRZuBJw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -138.00636812661475,
			"y": 439.6546951620794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.87995910644531,
			"height": 50,
			"seed": 35938147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729354,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Input\nMatch",
			"rawText": "Input\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "k0nVlyEKKpEzQMfE4or-W",
			"originalText": "Input\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 846,
			"versionNonce": 1782923373,
			"isDeleted": false,
			"id": "W0y3qlQCSZLf3VG61SJs_",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 61.32033017660797,
			"y": 396.6976639120794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 102.09765625,
			"height": 130.16015625,
			"seed": 1372093187,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "lv1ex2xW"
				}
			],
			"updated": 1704980729354,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 297,
			"versionNonce": 939460835,
			"isDeleted": false,
			"id": "lv1ex2xW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 81.18918851401031,
			"y": 424.2777420370794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.35993957519531,
			"height": 75,
			"seed": 967320227,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Device\n\n[S]",
			"rawText": "Device\n\n[S]",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "W0y3qlQCSZLf3VG61SJs_",
			"originalText": "Device\n\n[S]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 725,
			"versionNonce": 301771469,
			"isDeleted": false,
			"id": "7Dtvhzo_BPiPYBTtD7YZX",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 282.45704892660797,
			"y": 415.7953201620794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 1114756675,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "5QYF4Cgn"
				}
			],
			"updated": 1704980729355,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 275,
			"versionNonce": 428995715,
			"isDeleted": false,
			"id": "5QYF4Cgn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 298.65591672445953,
			"y": 440.1605545370794,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.69992065429688,
			"height": 50,
			"seed": 1526994403,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Output\nMatch",
			"rawText": "Output\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "7Dtvhzo_BPiPYBTtD7YZX",
			"originalText": "Output\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 350,
			"versionNonce": 2014824749,
			"isDeleted": false,
			"id": "cxBv3_Cqm57rTuOu0BKiX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -55.45896669839209,
			"y": 462.71914828707935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.00390625,
			"height": 0,
			"seed": 309158275,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					117.00390625,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 335,
			"versionNonce": 218524707,
			"isDeleted": false,
			"id": "zQeIWBvBawl1moCkIl-ec",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 165.67775205160797,
			"y": 462.94961703707935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.20703125,
			"height": 0,
			"seed": 300693795,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.20703125,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 366,
			"versionNonce": 2113936269,
			"isDeleted": false,
			"id": "7pdR8UkIasRm9FE-fbmWf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -159.7558416983921,
			"y": 463.71133578707935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.411876592399835,
			"height": 0,
			"seed": 1458511043,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-40.411876592399835,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 439,
			"versionNonce": 1984622531,
			"isDeleted": false,
			"id": "-J7qv85lmPekGA6iChMMq",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 498.31459337245695,
			"y": 463.9136757458607,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.99849105979035,
			"height": 0,
			"seed": 756321379,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-112.99849105979035,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 788,
			"versionNonce": 468656621,
			"isDeleted": false,
			"id": "GzKFCMhV3YQCpUxs2ot_O",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -194.86744482587875,
			"y": 462.97078402765976,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 1747650563,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "line",
			"version": 1003,
			"versionNonce": 931004259,
			"isDeleted": false,
			"id": "RBTbcxUZ97yNIQdMr9LIH",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": 535.238886250882,
			"y": 502.61644089729253,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 1580273571,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "ellipse",
			"version": 423,
			"versionNonce": 116284493,
			"isDeleted": false,
			"id": "Acc5nu6SoecWEfSDp2mj3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -284.392955436602,
			"y": 501.3244860446735,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.590205478603195,
			"height": 29.590205478603195,
			"seed": 559227715,
			"groupIds": [
				"MjFFMrEgLxEHCZy-_5NuC"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 700,
			"versionNonce": 1793989379,
			"isDeleted": false,
			"id": "bPcOvqaTb9yugEkLAywJa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -277.42861795666767,
			"y": 517.254767897336,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.62671951107037,
			"height": 13.263085679569341,
			"seed": 2046149347,
			"groupIds": [
				"MjFFMrEgLxEHCZy-_5NuC"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.395035361670153,
					-8.19912256579595
				],
				[
					12.787279608307504,
					5.063963113773392
				],
				[
					16.62671951107037,
					-2.3521404937578243
				]
			]
		},
		{
			"type": "line",
			"version": 309,
			"versionNonce": 383208109,
			"isDeleted": false,
			"id": "q4jc2L9tUpgbJi6FtgWCj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -270.47529266074895,
			"y": 463.2742732520383,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 547450499,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 377,
			"versionNonce": 1561969315,
			"isDeleted": false,
			"id": "HMdJKSq8xjjguCaIei1tA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -269.11162664966656,
			"y": 531.0727284707702,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 941008419,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 374,
			"versionNonce": 1817406733,
			"isDeleted": false,
			"id": "ZkbP4nv_KEnMol_raQ9Pf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -276.3831513048254,
			"y": 570.0603636985014,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 121891267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 505,
			"versionNonce": 1185904195,
			"isDeleted": false,
			"id": "_BlkPRGkm6mGWKFV8ziVE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 488.60498180717656,
			"y": 564.8862657330503,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 1934080355,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 362,
			"versionNonce": 1457275757,
			"isDeleted": false,
			"id": "8CfdZ_zZ1jepN60JWPZ9q",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 497.414416989681,
			"y": 540.604994942115,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 22.603366534780093,
			"seed": 963679491,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					22.603366534780093
				]
			]
		},
		{
			"type": "text",
			"version": 349,
			"versionNonce": 1183692259,
			"isDeleted": false,
			"id": "QPKOBAHj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 88.30168127846838,
			"y": 614.6298567054198,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 39.5999755859375,
			"height": 20,
			"seed": 1741416867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fig 3",
			"rawText": "Fig 3",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fig 3",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 361,
			"versionNonce": 2059095501,
			"isDeleted": false,
			"id": "vEHOG2Lv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -243.27526578618762,
			"y": 428.7525275008771,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 646233411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 454,
			"versionNonce": 465764739,
			"isDeleted": false,
			"id": "rJDjnpXB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 512.6125941032516,
			"y": 494.67663464373413,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 706878691,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 485,
			"versionNonce": 923405357,
			"isDeleted": false,
			"id": "5susUU3d",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -250.1061558967486,
			"y": 506.59181321516274,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.959976196289062,
			"height": 20,
			"seed": 2117240963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vs",
			"rawText": "Vs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vs",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 390,
			"versionNonce": 529389859,
			"isDeleted": false,
			"id": "0HB2qUp-JIv2QJfxtiyck",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -187.3974601989715,
			"y": 386.8297759337496,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 2086470851,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "line",
			"version": 463,
			"versionNonce": 1269956237,
			"isDeleted": false,
			"id": "_gOR-ticQXlAy1L48HFAw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 0.07689225293587754,
			"y": 387.1166062908924,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 360171043,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "line",
			"version": 551,
			"versionNonce": 2136784067,
			"isDeleted": false,
			"id": "7f5erFEjILhjVUoj76r1k",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 224.87672731348925,
			"y": 386.64562414803527,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 656658637,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "line",
			"version": 483,
			"versionNonce": 1064084717,
			"isDeleted": false,
			"id": "aBZTuNdmcthoOoW9DbtZ1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 418.96305296722153,
			"y": 385.7884812908924,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 364214467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "text",
			"version": 303,
			"versionNonce": 919481443,
			"isDeleted": false,
			"id": "kKx8OD8M",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -229.39299591325724,
			"y": 578.5544550632139,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 121.74615478515625,
			"height": 32.401785714285595,
			"seed": 40178883,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power available\nfrom source (Pavs)",
			"rawText": "Power available\nfrom source (Pavs)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power available\nfrom source (Pavs)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 387,
			"versionNonce": 96698189,
			"isDeleted": false,
			"id": "MZQoFuBl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -53.74487442686572,
			"y": 577.5656157774994,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 111.93536376953125,
			"height": 32.401785714285595,
			"seed": 1956573005,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power delivered\nto the input (Pin)",
			"rawText": "Power delivered\nto the input (Pin)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power delivered\nto the input (Pin)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 542,
			"versionNonce": 1236314115,
			"isDeleted": false,
			"id": "GrKUB8x4",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 155.3022686305486,
			"y": 573.1839193489282,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 154.72930908203125,
			"height": 32.401785714285595,
			"seed": 350003629,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power available\nfrom the network (Pavn)",
			"rawText": "Power available\nfrom the network (Pavn)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power available\nfrom the network (Pavn)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 455,
			"versionNonce": 1695550893,
			"isDeleted": false,
			"id": "9G3lNOd3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 360.8513757734058,
			"y": 576.7107050632139,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 107.45127868652344,
			"height": 32.401785714285595,
			"seed": 1451586125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power delivered\nto the load (PL)",
			"rawText": "Power delivered\nto the load (PL)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power delivered\nto the load (PL)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "arrow",
			"version": 158,
			"versionNonce": 1040363427,
			"isDeleted": false,
			"id": "VfmGjBl1l2UHmFbLBtb_G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 2.227539801028456,
			"y": 403.1973122060709,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 28.801339285714278,
			"height": 0,
			"seed": 167932557,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					28.801339285714278,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 235,
			"versionNonce": 477876237,
			"isDeleted": false,
			"id": "x96L_4K_Mx1ASbrIE9Ovd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 225.3023165867427,
			"y": 401.58062761049365,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 28.801339285714278,
			"height": 0,
			"seed": 234837699,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					28.801339285714278,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 220,
			"versionNonce": 1441973059,
			"isDeleted": false,
			"id": "OGYS9nPXcb0kKgrvEInd2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 420.025530872457,
			"y": 402.0136633247793,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 28.801339285714278,
			"height": 0,
			"seed": 1210396717,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					28.801339285714278,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 471,
			"versionNonce": 401539181,
			"isDeleted": false,
			"id": "Wz-4_AoMj78D5VhyDzzhi",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -186.72446912754296,
			"y": 402.3881825561139,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 143.04818302624264,
			"height": 0,
			"seed": 362023373,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "k0nVlyEKKpEzQMfE4or-W",
				"gap": 12.901278230965488,
				"focus": 1.2613434007617932
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					143.04818302624264,
					0
				]
			]
		},
		{
			"type": "rectangle",
			"version": 755,
			"versionNonce": 165634787,
			"isDeleted": false,
			"id": "o7eAQxr-Pk8e5O3qoWCUO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -171.41984288790684,
			"y": 739.0907239890292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 697254253,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "cFcuYJbG"
				},
				{
					"id": "odKilT0copmCNiaFo4bhW",
					"type": "arrow"
				},
				{
					"id": "uF1s-NeCiPlr17fHzNwUs",
					"type": "arrow"
				}
			],
			"updated": 1704980729355,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 393,
			"versionNonce": 275181773,
			"isDeleted": false,
			"id": "cFcuYJbG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -150.3109943161295,
			"y": 763.4559583640292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.87995910644531,
			"height": 50,
			"seed": 979274701,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Input\nMatch",
			"rawText": "Input\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "o7eAQxr-Pk8e5O3qoWCUO",
			"originalText": "Input\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 963,
			"versionNonce": 1113001603,
			"isDeleted": false,
			"id": "BfyjLrkGUt92-PQHti19G",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 49.015703987093275,
			"y": 720.4952740160935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 102.09765625,
			"height": 130.16015625,
			"seed": 1536526893,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "3QgVMamb"
				},
				{
					"id": "hSObC0Uq5QAcKLAqQiAMC",
					"type": "arrow"
				},
				{
					"id": "SCQW8U_Bjmyqdnw6eYq7x",
					"type": "arrow"
				}
			],
			"updated": 1704980729355,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 412,
			"versionNonce": 2101956397,
			"isDeleted": false,
			"id": "3QgVMamb",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 68.88456232449562,
			"y": 748.0753521410935,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.35993957519531,
			"height": 75,
			"seed": 236829837,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Device\n\n[S]",
			"rawText": "Device\n\n[S]",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "BfyjLrkGUt92-PQHti19G",
			"originalText": "Device\n\n[S]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 839,
			"versionNonce": 1377322531,
			"isDeleted": false,
			"id": "bZ2B4DwkPuQ07wNpM8Nfl",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 270.1524227370933,
			"y": 739.5965833640292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 2041619181,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "qfDlzDFa"
				},
				{
					"id": "PI5Tgoq6OmU8PQgf2p7F-",
					"type": "arrow"
				}
			],
			"updated": 1704980729355,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 388,
			"versionNonce": 789635469,
			"isDeleted": false,
			"id": "qfDlzDFa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 286.35129053494484,
			"y": 763.9618177390292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.69992065429688,
			"height": 50,
			"seed": 316128589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Output\nMatch",
			"rawText": "Output\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "bZ2B4DwkPuQ07wNpM8Nfl",
			"originalText": "Output\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 463,
			"versionNonce": 806455747,
			"isDeleted": false,
			"id": "Dw6KSrwoJ7gUy9WaVAb5M",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -67.76359288790684,
			"y": 786.5204114890292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.00390625,
			"height": 0,
			"seed": 15502253,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					117.00390625,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 448,
			"versionNonce": 989276141,
			"isDeleted": false,
			"id": "sINwHIl-RXrn4HLe3CxGe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 153.37312586209327,
			"y": 786.7508802390292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.20703125,
			"height": 0,
			"seed": 1142459917,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.20703125,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 479,
			"versionNonce": 1902205283,
			"isDeleted": false,
			"id": "WhF4FrZXFuBqEWZ106ow3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -172.06046788790684,
			"y": 787.5125989890292,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.411876592399835,
			"height": 0,
			"seed": 458572909,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-40.411876592399835,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 552,
			"versionNonce": 1392878157,
			"isDeleted": false,
			"id": "ZmEfo1-hDIrMvoEGDfgbg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 486.00996718294226,
			"y": 787.7149389478108,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.99849105979035,
			"height": 0,
			"seed": 711732941,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-112.99849105979035,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 901,
			"versionNonce": 55981315,
			"isDeleted": false,
			"id": "AqN2ozSEcB7TRdqR2mG57",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -207.1720710153935,
			"y": 786.7720472296097,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 1610009901,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "line",
			"version": 1116,
			"versionNonce": 739627181,
			"isDeleted": false,
			"id": "j58cYWUwkqfK5M8qdAy_Z",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": 522.9342600613674,
			"y": 826.4177040992425,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 459186061,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "ellipse",
			"version": 536,
			"versionNonce": 628006051,
			"isDeleted": false,
			"id": "NtZF7TVhVP2X-t3qGlxpG",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -296.69758162611663,
			"y": 825.1257492466235,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.590205478603195,
			"height": 29.590205478603195,
			"seed": 316483053,
			"groupIds": [
				"1kWBkA0l46zMEJEG_EL9r"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 813,
			"versionNonce": 600912653,
			"isDeleted": false,
			"id": "PUQ7Y3F9S_EBDFA--2P9G",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -289.7332441461823,
			"y": 841.0560310992859,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.62671951107037,
			"height": 13.263085679569341,
			"seed": 2038161485,
			"groupIds": [
				"1kWBkA0l46zMEJEG_EL9r"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729355,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.395035361670153,
					-8.19912256579595
				],
				[
					12.787279608307504,
					5.063963113773392
				],
				[
					16.62671951107037,
					-2.3521404937578243
				]
			]
		},
		{
			"type": "line",
			"version": 422,
			"versionNonce": 593039427,
			"isDeleted": false,
			"id": "7tRzJlviLFwOHHaHGDnJ0",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -282.7799188502637,
			"y": 787.0755364539883,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1695829677,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 490,
			"versionNonce": 649152877,
			"isDeleted": false,
			"id": "gOHJMJ-rfJcX2Pn1dCvdw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -281.4162528391813,
			"y": 854.8739916727203,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1951396109,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 487,
			"versionNonce": 1324617699,
			"isDeleted": false,
			"id": "7v5NMwvQqYD00Ku7PRlFV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -288.68777749434014,
			"y": 893.8616269004514,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 883443565,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 618,
			"versionNonce": 1442812877,
			"isDeleted": false,
			"id": "xNHG2EN36CqeNVEJFpGQv",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 476.30035561766186,
			"y": 888.6875289350004,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 1214697933,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 475,
			"versionNonce": 978197379,
			"isDeleted": false,
			"id": "qY0Lc0VeGKRCbuowVtuzZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 485.1097908001663,
			"y": 864.406258144065,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 22.603366534780093,
			"seed": 1285885997,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					22.603366534780093
				]
			]
		},
		{
			"type": "text",
			"version": 464,
			"versionNonce": 1842713133,
			"isDeleted": false,
			"id": "DDZFW22V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 75.99705508895374,
			"y": 938.4311199073699,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.9439697265625,
			"height": 20,
			"seed": 2135720589,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fig 4",
			"rawText": "Fig 4",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fig 4",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 474,
			"versionNonce": 832942883,
			"isDeleted": false,
			"id": "TC1oIKKx",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -255.57989197570225,
			"y": 752.5537907028271,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 622242029,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 567,
			"versionNonce": 1797047437,
			"isDeleted": false,
			"id": "u5cgdFOF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 500.3079679137369,
			"y": 818.4778978456842,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 797770573,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 598,
			"versionNonce": 1969837763,
			"isDeleted": false,
			"id": "JkSlILXK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -262.41078208626334,
			"y": 830.3930764171126,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.959976196289062,
			"height": 20,
			"seed": 587796909,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vs",
			"rawText": "Vs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vs",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 503,
			"versionNonce": 1905175277,
			"isDeleted": false,
			"id": "g6WbkuRdwi8joUyzZZzr6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199.70208638848624,
			"y": 710.6310391356996,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 1018450957,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "line",
			"version": 596,
			"versionNonce": 876054115,
			"isDeleted": false,
			"id": "tNHysWzyuQGG73yA23HkP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 406.65842677770684,
			"y": 709.5897444928422,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 1151357741,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "text",
			"version": 416,
			"versionNonce": 1907672397,
			"isDeleted": false,
			"id": "k95tgMP9",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -241.6976221027719,
			"y": 902.3557182651638,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 121.74615478515625,
			"height": 32.401785714285595,
			"seed": 2095539597,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power available\nfrom source (Pavs)",
			"rawText": "Power available\nfrom source (Pavs)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power available\nfrom source (Pavs)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 568,
			"versionNonce": 1155449347,
			"isDeleted": false,
			"id": "eaoWb20V",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 348.5467495838911,
			"y": 900.5119682651638,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 107.45127868652344,
			"height": 32.401785714285595,
			"seed": 1573573805,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power delivered\nto the load (PL)",
			"rawText": "Power delivered\nto the load (PL)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power delivered\nto the load (PL)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "arrow",
			"version": 566,
			"versionNonce": 250123181,
			"isDeleted": false,
			"id": "FxbMFe2_aV5JwmWpJH2pj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 406.990285095834,
			"y": 726.5382399179663,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 19.422577804285652,
			"height": 0.08551676166405286,
			"seed": 438507469,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "byU8f6LszLN2YiyY4MxFI",
				"focus": 0.7616490072266913,
				"gap": 4.771516536808576
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					19.422577804285652,
					-0.08551676166405286
				]
			]
		},
		{
			"type": "arrow",
			"version": 682,
			"versionNonce": 1684957901,
			"isDeleted": false,
			"id": "odKilT0copmCNiaFo4bhW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -199.02909531705768,
			"y": 726.1894457580639,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 24.21122046762082,
			"height": 3.410605131648481e-13,
			"seed": 1793627693,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "o7eAQxr-Pk8e5O3qoWCUO",
				"gap": 13.341274347091769,
				"focus": 1.2613434007617943
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					24.21122046762082,
					-3.410605131648481e-13
				]
			]
		},
		{
			"type": "text",
			"version": 77,
			"versionNonce": 1163105805,
			"isDeleted": false,
			"id": "X3Lz3LFI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 34.35086253109023,
			"y": 681.1524853715498,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e6fcf5",
			"width": 130.7039337158203,
			"height": 20,
			"seed": 72779331,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729356,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Transducer Gain",
			"rawText": "Transducer Gain",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Transducer Gain",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 820,
			"versionNonce": 1865473731,
			"isDeleted": false,
			"id": "EsZy0HatYYUT556wctJQG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -211.20406538039674,
			"y": 1413.081515959764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 2077728899,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "LQvFSWJ1"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 456,
			"versionNonce": 466488931,
			"isDeleted": false,
			"id": "LQvFSWJ1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -190.0952168086194,
			"y": 1437.446750334764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.87995910644531,
			"height": 50,
			"seed": 1907791907,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Input\nMatch",
			"rawText": "Input\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "EsZy0HatYYUT556wctJQG",
			"originalText": "Input\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 1026,
			"versionNonce": 140790275,
			"isDeleted": false,
			"id": "eYsc6p0iHVxK5xSQlJ6UP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.231481494603258,
			"y": 1394.489719084764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 102.09765625,
			"height": 130.16015625,
			"seed": 739613635,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "YSx0huv2"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 473,
			"versionNonce": 1777471907,
			"isDeleted": false,
			"id": "YSx0huv2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 29.100339832005602,
			"y": 1422.069797209764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.35993957519531,
			"height": 75,
			"seed": 924003171,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Device\n\n[S]",
			"rawText": "Device\n\n[S]",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "eYsc6p0iHVxK5xSQlJ6UP",
			"originalText": "Device\n\n[S]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 903,
			"versionNonce": 1369826627,
			"isDeleted": false,
			"id": "24H3NNMfTRK32q7TEiNpZ",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 230.36820024460326,
			"y": 1413.587375334764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 385730307,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "3YiJSVqY"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 451,
			"versionNonce": 652100835,
			"isDeleted": false,
			"id": "3YiJSVqY",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 246.56706804245482,
			"y": 1437.952609709764,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.69992065429688,
			"height": 50,
			"seed": 1112796835,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Output\nMatch",
			"rawText": "Output\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "24H3NNMfTRK32q7TEiNpZ",
			"originalText": "Output\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 526,
			"versionNonce": 1630122115,
			"isDeleted": false,
			"id": "aKM04EwJffsi2ei6XnDlE",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -107.5478153803968,
			"y": 1460.5112034597635,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.00390625,
			"height": 0,
			"seed": 1539580483,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					117.00390625,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 511,
			"versionNonce": 38184995,
			"isDeleted": false,
			"id": "ARrqYv8ZL498tFjHq2FO6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 113.58890336960326,
			"y": 1460.7416722097635,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.20703125,
			"height": 0,
			"seed": 741138915,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.20703125,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 542,
			"versionNonce": 1344515011,
			"isDeleted": false,
			"id": "SexvAj7a0oHi6S9QJMHtA",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -211.84469038039674,
			"y": 1461.5033909597635,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.411876592399835,
			"height": 0,
			"seed": 1553771907,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-40.411876592399835,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 615,
			"versionNonce": 1323252579,
			"isDeleted": false,
			"id": "Uej3aWWKqBwZ3JeGOtSfa",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 446.22574469045225,
			"y": 1461.705730918545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.99849105979035,
			"height": 0,
			"seed": 1884423459,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-112.99849105979035,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 964,
			"versionNonce": 2059917059,
			"isDeleted": false,
			"id": "8zhJAiHudqFqQ7VXh8X_i",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -246.9562935078834,
			"y": 1460.7628392003442,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 2126211267,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "line",
			"version": 1179,
			"versionNonce": 1113325219,
			"isDeleted": false,
			"id": "DIY_-eLyVGnm5l4DPwCBg",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": 483.15003756887734,
			"y": 1500.4084960699768,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 762796131,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "ellipse",
			"version": 625,
			"versionNonce": 1325606925,
			"isDeleted": false,
			"id": "oyzaZ9R4WOuhkvF0sWhhf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -336.50297550152334,
			"y": 1499.4129405781896,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.590205478603195,
			"height": 29.590205478603195,
			"seed": 1783911427,
			"groupIds": [
				"AaL79cliEf8iy1vVeGo7P"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981552232,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 902,
			"versionNonce": 1641848429,
			"isDeleted": false,
			"id": "Vn4SO2-StkYsDt2IACaiK",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -329.538638021589,
			"y": 1515.3432224308522,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.62671951107037,
			"height": 13.263085679569341,
			"seed": 1699797923,
			"groupIds": [
				"AaL79cliEf8iy1vVeGo7P"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981552232,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.395035361670153,
					-8.19912256579595
				],
				[
					12.787279608307504,
					5.063963113773392
				],
				[
					16.62671951107037,
					-2.3521404937578243
				]
			]
		},
		{
			"type": "line",
			"version": 485,
			"versionNonce": 1078604355,
			"isDeleted": false,
			"id": "JPY0GcbpiEWqzRebdrIPt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -322.5641413427536,
			"y": 1461.0663284247228,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1251700547,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 553,
			"versionNonce": 896594403,
			"isDeleted": false,
			"id": "oZvv2dFF29nHLCefY62cc",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -321.2004753316712,
			"y": 1528.8647836434545,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1016237795,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 562,
			"versionNonce": 103311651,
			"isDeleted": false,
			"id": "wGjTyCeh3ZWucx3ibq4Ho",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -328.3414431255114,
			"y": 1567.9794471686848,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 230996611,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981557735,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 681,
			"versionNonce": 1121893763,
			"isDeleted": false,
			"id": "M40gxJfwDdjP6y8yPpV7F",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 436.51613312517185,
			"y": 1562.6783209057346,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 988836387,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 538,
			"versionNonce": 1674712355,
			"isDeleted": false,
			"id": "vBbWpDyjybcRlq9OtKa2z",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 445.3255683076763,
			"y": 1538.3970501147994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 22.603366534780093,
			"seed": 621032899,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					22.603366534780093
				]
			]
		},
		{
			"type": "text",
			"version": 537,
			"versionNonce": 666466499,
			"isDeleted": false,
			"id": "fIFR4eoI",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -295.3641144681924,
			"y": 1426.5445826735615,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 186549603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 630,
			"versionNonce": 741566563,
			"isDeleted": false,
			"id": "OIWtXDYQ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 460.5237454212469,
			"y": 1492.4686898164184,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 1150148867,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 661,
			"versionNonce": 1460560899,
			"isDeleted": false,
			"id": "yTu04cRP",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -302.19500457875324,
			"y": 1504.3838683878469,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.959976196289062,
			"height": 20,
			"seed": 986761379,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vs",
			"rawText": "Vs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vs",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 639,
			"versionNonce": 1346956195,
			"isDeleted": false,
			"id": "6LRZY5yelqLwE3h22Jbjw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -52.011956429068846,
			"y": 1384.908661463577,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 2059090915,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "line",
			"version": 659,
			"versionNonce": 1007779651,
			"isDeleted": false,
			"id": "fqgojSYmqo0t5OdognMEW",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 366.8742042852168,
			"y": 1383.580536463577,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 1586618147,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "text",
			"version": 563,
			"versionNonce": 885432035,
			"isDeleted": false,
			"id": "0KQqi1bu",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -105.83372310887046,
			"y": 1575.3576709501838,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 111.93536376953125,
			"height": 32.401785714285595,
			"seed": 487109219,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power delivered\nto the input (Pin)",
			"rawText": "Power delivered\nto the input (Pin)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power delivered\nto the input (Pin)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 631,
			"versionNonce": 83282563,
			"isDeleted": false,
			"id": "OMoOXOgk",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 308.76252709140107,
			"y": 1574.5027602358984,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 107.45127868652344,
			"height": 32.401785714285595,
			"seed": 1339274659,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power delivered\nto the load (PL)",
			"rawText": "Power delivered\nto the load (PL)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power delivered\nto the load (PL)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "arrow",
			"version": 334,
			"versionNonce": 559972899,
			"isDeleted": false,
			"id": "ZamKf1ryDA863uNt99oak",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -49.86130888097625,
			"y": 1400.9893673787553,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 28.801339285714278,
			"height": 0,
			"seed": 1404242243,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					28.801339285714278,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 584,
			"versionNonce": 659339149,
			"isDeleted": false,
			"id": "PdlkrnZZ7i6y8eZpmt4Sp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 367.9366821904523,
			"y": 1399.8057184974634,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 22.559441470063348,
			"height": 0,
			"seed": 356373635,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737772,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "6l0Uft3sYyMUngjZd7q00",
				"focus": 0.823395318077939,
				"gap": 15.803322220877646
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					22.559441470063348,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 583,
			"versionNonce": 13276515,
			"isDeleted": false,
			"id": "rwx30Frf",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 40.08692054652397,
			"y": 1625.3036103757552,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.59196472167969,
			"height": 20,
			"seed": 1348536451,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fig 5",
			"rawText": "Fig 5",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fig 5",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 316,
			"versionNonce": 1245180163,
			"isDeleted": false,
			"id": "4qMdQujm",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": 136.72133273004943,
			"y": 1358.286031884081,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e6fcf5",
			"width": 87.08795166015625,
			"height": 20,
			"seed": 1664161581,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Power Gain",
			"rawText": "Power Gain",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power Gain",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "rectangle",
			"version": 865,
			"versionNonce": 1672650083,
			"isDeleted": false,
			"id": "PvHOdaMN3aBpBsJ1ZPXNd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -230.3123945169026,
			"y": 2024.3467340293191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 730963875,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "uETzzINZ"
				},
				{
					"id": "q1cAXUK7TVOQBYZhHGbLN",
					"type": "arrow"
				}
			],
			"updated": 1704981650671,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 503,
			"versionNonce": 916670157,
			"isDeleted": false,
			"id": "uETzzINZ",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -209.20354594512526,
			"y": 2048.711968404319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 59.87995910644531,
			"height": 50,
			"seed": 337883971,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Input\nMatch",
			"rawText": "Input\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "PvHOdaMN3aBpBsJ1ZPXNd",
			"originalText": "Input\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "rectangle",
			"version": 1070,
			"versionNonce": 1597956259,
			"isDeleted": false,
			"id": "gZ4e3HxOoYmJKV-jgU10m",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -9.876847641902486,
			"y": 2005.7549371543191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffec99",
			"width": 102.09765625,
			"height": 130.16015625,
			"seed": 879907555,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "wpSg3arN"
				}
			],
			"updated": 1704981650671,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 521,
			"versionNonce": 1115739203,
			"isDeleted": false,
			"id": "wpSg3arN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 9.992010695499857,
			"y": 2033.3350152793191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 62.35993957519531,
			"height": 75,
			"seed": 2097938051,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981650671,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Device\n\n[S]",
			"rawText": "Device\n\n[S]",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "gZ4e3HxOoYmJKV-jgU10m",
			"originalText": "Device\n\n[S]",
			"lineHeight": 1.25,
			"baseline": 68
		},
		{
			"type": "rectangle",
			"version": 949,
			"versionNonce": 1015239651,
			"isDeleted": false,
			"id": "yzVlgKO7Ol76UVqfjHUDG",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 211.2598711080975,
			"y": 2024.8525934043191,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#a5d8ff",
			"width": 102.09765625,
			"height": 98.73046875,
			"seed": 1219442211,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 3
			},
			"boundElements": [
				{
					"type": "text",
					"id": "dnEMPRIS"
				}
			],
			"updated": 1704981650671,
			"link": null,
			"locked": false
		},
		{
			"type": "text",
			"version": 498,
			"versionNonce": 1943824045,
			"isDeleted": false,
			"id": "dnEMPRIS",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 227.45873890594908,
			"y": 2049.217827779319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 69.69992065429688,
			"height": 50,
			"seed": 373979587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 20,
			"fontFamily": 1,
			"text": "Output\nMatch",
			"rawText": "Output\nMatch",
			"textAlign": "center",
			"verticalAlign": "middle",
			"containerId": "yzVlgKO7Ol76UVqfjHUDG",
			"originalText": "Output\nMatch",
			"lineHeight": 1.25,
			"baseline": 43
		},
		{
			"type": "line",
			"version": 573,
			"versionNonce": 575998221,
			"isDeleted": false,
			"id": "2Nye5BQMXt3USFw8cjZE2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -126.6561445169026,
			"y": 2071.776421529319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 117.00390625,
			"height": 0,
			"seed": 50088291,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					117.00390625,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 558,
			"versionNonce": 306863981,
			"isDeleted": false,
			"id": "YJ0e-Qq-9c5pYBHB7ha15",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 94.48057423309751,
			"y": 2072.006890279319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 118.20703125,
			"height": 0,
			"seed": 68363523,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					118.20703125,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 589,
			"versionNonce": 1510336973,
			"isDeleted": false,
			"id": "UPCNM88x23TE1GtWsEaAt",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -230.9530195169026,
			"y": 2072.768609029319,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 40.411876592399835,
			"height": 0,
			"seed": 1628277923,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-40.411876592399835,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 662,
			"versionNonce": 178333741,
			"isDeleted": false,
			"id": "NTAIvgjwo89-MPovmN12L",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 427.1174155539465,
			"y": 2072.9709489881006,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 112.99849105979035,
			"height": 0,
			"seed": 1838809155,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-112.99849105979035,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 1011,
			"versionNonce": 1443207821,
			"isDeleted": false,
			"id": "RIi_Q7DQMb1LNs41l_YIo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -266.06462264438926,
			"y": 2072.0280572698994,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 60227555,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "line",
			"version": 1226,
			"versionNonce": 1961672941,
			"isDeleted": false,
			"id": "IaroNku4g7WwYfMDu_nrd",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 1.5707963267948957,
			"x": 464.0417084323716,
			"y": 2111.6737141395324,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 76.22672261366138,
			"height": 21.242978313977318,
			"seed": 1024658307,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-20.076922672657588,
					-0.1243811825426544
				],
				[
					-25.076060343751696,
					-9.901231269877183
				],
				[
					-27.793919499470594,
					10.576243754912053
				],
				[
					-35.478767530971105,
					-10.666734559065265
				],
				[
					-40.67529880528399,
					10.471777536989988
				],
				[
					-48.03351507640948,
					-10.349842051856879
				],
				[
					-53.027508940253554,
					10.571352360092957
				],
				[
					-58.68698286706647,
					0.03249283701254946
				],
				[
					-76.22672261366138,
					-0.5342101913138126
				]
			]
		},
		{
			"type": "ellipse",
			"version": 646,
			"versionNonce": 1289755469,
			"isDeleted": false,
			"id": "pJxGwbQu7omYWWz5e037j",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -355.5901332551124,
			"y": 2110.3817592869136,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 29.590205478603195,
			"height": 29.590205478603195,
			"seed": 1850516259,
			"groupIds": [
				"TXIYlYKd_1RzLoaKp7pXz"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false
		},
		{
			"type": "line",
			"version": 923,
			"versionNonce": 1446586797,
			"isDeleted": false,
			"id": "53npAsgGuaAQZb774gX9g",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -348.62579577517806,
			"y": 2126.3120411395757,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.62671951107037,
			"height": 13.263085679569341,
			"seed": 1605519043,
			"groupIds": [
				"TXIYlYKd_1RzLoaKp7pXz"
			],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					4.395035361670153,
					-8.19912256579595
				],
				[
					12.787279608307504,
					5.063963113773392
				],
				[
					16.62671951107037,
					-2.3521404937578243
				]
			]
		},
		{
			"type": "line",
			"version": 532,
			"versionNonce": 1109486605,
			"isDeleted": false,
			"id": "9VEcaGzPtVCP5IMfAvq-6",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -341.67247047925946,
			"y": 2072.331546494278,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 1206023779,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 600,
			"versionNonce": 1620206189,
			"isDeleted": false,
			"id": "GJ-pXBy4ta4snULY91Ux2",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -340.3088044681771,
			"y": 2140.1300017130106,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0.4012346734317589,
			"height": 38.36141868695944,
			"seed": 95138307,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0.4012346734317589,
					38.36141868695944
				]
			]
		},
		{
			"type": "line",
			"version": 597,
			"versionNonce": 1180011725,
			"isDeleted": false,
			"id": "mD3KYKqOZZdE0s1TEaOGL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -347.5803291233359,
			"y": 2179.1176369407412,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 437025187,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 728,
			"versionNonce": 855927597,
			"isDeleted": false,
			"id": "SMDmD_oRcG2hzAnbA7fdj",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 417.4078039886661,
			"y": 2173.9435389752907,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.741910178079706,
			"height": 12.316962282086081,
			"seed": 1647529283,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					16.741910178079706,
					-0.5281834602249376
				],
				[
					7.224571153694171,
					11.788778821861143
				],
				[
					0,
					0
				]
			]
		},
		{
			"type": "line",
			"version": 585,
			"versionNonce": 923303309,
			"isDeleted": false,
			"id": "8wiZOPMJxs6ZCLPEJFKMe",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 426.21723917117055,
			"y": 2149.6622681843546,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 0,
			"height": 22.603366534780093,
			"seed": 293514467,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					0,
					22.603366534780093
				]
			]
		},
		{
			"type": "text",
			"version": 577,
			"versionNonce": 429605869,
			"isDeleted": false,
			"id": "mAS9qyZn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 17.104503459957925,
			"y": 2223.6871299476597,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 38.9439697265625,
			"height": 20,
			"seed": 1803360387,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Fig 6",
			"rawText": "Fig 6",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Fig 6",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 584,
			"versionNonce": 2126921293,
			"isDeleted": false,
			"id": "Rnmo0jz3",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -314.472443604698,
			"y": 2037.809800743117,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 1038946339,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 677,
			"versionNonce": 1298328749,
			"isDeleted": false,
			"id": "EsROzqvF",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 441.4154162847411,
			"y": 2103.733907885974,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 23.759994506835938,
			"height": 20,
			"seed": 448598979,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Z0",
			"rawText": "Z0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Z0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 708,
			"versionNonce": 1427820301,
			"isDeleted": false,
			"id": "XWNyCIXl",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -321.3033337152591,
			"y": 2115.6490864574025,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"width": 16.959976196289062,
			"height": 20,
			"seed": 1376494435,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Vs",
			"rawText": "Vs",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Vs",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "line",
			"version": 613,
			"versionNonce": 879191405,
			"isDeleted": false,
			"id": "HDLyYDmcUP6IqKAWQOMsn",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -258.594638017482,
			"y": 1995.8870491759897,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 740769539,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "line",
			"version": 774,
			"versionNonce": 2123509709,
			"isDeleted": false,
			"id": "caHaPGlo7EuHRzBHxInrV",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 153.6795494949788,
			"y": 1995.7028973902754,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 1.4210854715202004e-14,
			"height": 179.7834821428571,
			"seed": 1592760899,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": null,
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": null,
			"points": [
				[
					0,
					0
				],
				[
					-1.4210854715202004e-14,
					179.7834821428571
				]
			]
		},
		{
			"type": "text",
			"version": 526,
			"versionNonce": 565489197,
			"isDeleted": false,
			"id": "9y2bg1lL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -300.59017373176766,
			"y": 2187.6117283054537,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 121.74615478515625,
			"height": 32.401785714285595,
			"seed": 894051715,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power available\nfrom source (Pavs)",
			"rawText": "Power available\nfrom source (Pavs)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power available\nfrom source (Pavs)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "text",
			"version": 765,
			"versionNonce": 213409933,
			"isDeleted": false,
			"id": "sR2Ps12v",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "dashed",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 84.10509081203816,
			"y": 2182.2411925911683,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 154.72930908203125,
			"height": 32.401785714285595,
			"seed": 879419587,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 12.960714285714237,
			"fontFamily": 1,
			"text": "Power available\nfrom the network (Pavn)",
			"rawText": "Power available\nfrom the network (Pavn)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Power available\nfrom the network (Pavn)",
			"lineHeight": 1.25,
			"baseline": 27
		},
		{
			"type": "arrow",
			"version": 641,
			"versionNonce": 1194099011,
			"isDeleted": false,
			"id": "bUFCcvfbJqHGBuoXXctiX",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 154.10513876823225,
			"y": 2010.6379008527335,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 28.801339285714278,
			"height": 0,
			"seed": 1251169187,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547724,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "yA4IAfjQq97YykS6w6UlW",
				"focus": 0.8188408997627565,
				"gap": 17.28018559897228
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					28.801339285714278,
					0
				]
			]
		},
		{
			"type": "arrow",
			"version": 855,
			"versionNonce": 1781598893,
			"isDeleted": false,
			"id": "q1cAXUK7TVOQBYZhHGbLN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -257.92164694605344,
			"y": 2011.4454557983538,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 27.609250820929617,
			"height": 0,
			"seed": 496436963,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": null,
			"endBinding": {
				"elementId": "PvHOdaMN3aBpBsJ1ZPXNd",
				"gap": 12.901278230965431,
				"focus": 1.2613434007617903
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					27.609250820929617,
					0
				]
			]
		},
		{
			"type": "text",
			"version": 434,
			"versionNonce": 2086252461,
			"isDeleted": false,
			"id": "uqsoWSNw",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 2,
			"opacity": 100,
			"angle": 0,
			"x": -111.46772417871591,
			"y": 1966.5706238530795,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#e6fcf5",
			"width": 111.27993774414062,
			"height": 20,
			"seed": 1340096803,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981547723,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "Available Gain",
			"rawText": "Available Gain",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "Available Gain",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 595,
			"versionNonce": 374442285,
			"isDeleted": false,
			"id": "uF1s-NeCiPlr17fHzNwUs",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -41.35572921278342,
			"y": 884.9885369461566,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.510874808381402,
			"height": 65.93186640283365,
			"seed": 1146935853,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "hH8ceX4IAO6wfsPxWZwoT",
				"focus": 0.22301495824807077,
				"gap": 13.391633605139418
			},
			"endBinding": {
				"elementId": "o7eAQxr-Pk8e5O3qoWCUO",
				"gap": 3.0165304947516063,
				"focus": 0.6837077503724571
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					0.5609478780095944,
					-65.93186640283365
				],
				[
					-24.94992693037181,
					-64.13267503207851
				]
			]
		},
		{
			"type": "arrow",
			"version": 670,
			"versionNonce": 788650893,
			"isDeleted": false,
			"id": "hSObC0Uq5QAcKLAqQiAMC",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 20.008269912938545,
			"y": 889.6679050221605,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 25.988605022743247,
			"height": 75.32365604633647,
			"seed": 24841357,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ktRGKOZKitfeVeRpcwo6-",
				"focus": -0.15948761301907377,
				"gap": 10.926089310881025
			},
			"endBinding": {
				"elementId": "BfyjLrkGUt92-PQHti19G",
				"gap": 5.701387992037695,
				"focus": -0.5038436986016984
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-2.682558940626218,
					-75.32365604633647
				],
				[
					23.306046082117028,
					-73.4907720607381
				]
			]
		},
		{
			"type": "arrow",
			"version": 466,
			"versionNonce": 1186521581,
			"isDeleted": false,
			"id": "SCQW8U_Bjmyqdnw6eYq7x",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 177.79729472580712,
			"y": 890.0445757805438,
			"strokeColor": "#1971c2",
			"backgroundColor": "transparent",
			"width": 25.510874808381402,
			"height": 74.22621421050621,
			"seed": 887354093,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "ICGJVWXO6Wh1i1B4GurkM",
				"focus": 0.1829183486730898,
				"gap": 6.987030855366129
			},
			"endBinding": {
				"elementId": "BfyjLrkGUt92-PQHti19G",
				"gap": 3.8080456240267324,
				"focus": 0.5228722690164842
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					2.6349859436942893,
					-74.22621421050621
				],
				[
					-22.875888864687113,
					-72.4270228397512
				]
			]
		},
		{
			"type": "arrow",
			"version": 660,
			"versionNonce": 847256653,
			"isDeleted": false,
			"id": "PI5Tgoq6OmU8PQgf2p7F-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 243.38957553442026,
			"y": 890.1392875335736,
			"strokeColor": "#e03131",
			"backgroundColor": "transparent",
			"width": 25.98860502274326,
			"height": 75.61621378881954,
			"seed": 723586381,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983129303,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "2t5pTtbbVdpWeF9v3f31l",
				"focus": -0.09378688749997223,
				"gap": 8.647156324455409
			},
			"endBinding": {
				"elementId": "bZ2B4DwkPuQ07wNpM8Nfl",
				"gap": 3.458572272312665,
				"focus": -0.5897865110918717
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					-2.6843300923829103,
					-75.61621378881954
				],
				[
					23.30427493036035,
					-73.78332980322136
				]
			]
		},
		{
			"type": "image",
			"version": 272,
			"versionNonce": 828739907,
			"isDeleted": false,
			"id": "hH8ceX4IAO6wfsPxWZwoT",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -72.73978980180223,
			"y": 898.380170551296,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 51,
			"height": 16,
			"seed": 1670110125,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "uF1s-NeCiPlr17fHzNwUs",
					"type": "arrow"
				}
			],
			"updated": 1704980729357,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "6bc4b548241eef3f8aab8900f6b04d3dc1d66377",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 291,
			"versionNonce": 778655853,
			"isDeleted": false,
			"id": "2t5pTtbbVdpWeF9v3f31l",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 220.44563366720706,
			"y": 898.786443858029,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 52,
			"height": 16,
			"seed": 911072781,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "PI5Tgoq6OmU8PQgf2p7F-",
					"type": "arrow"
				}
			],
			"updated": 1704980729357,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d4bf9232f310046a402d644884d8957ff3774dce",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 183,
			"versionNonce": 1237872867,
			"isDeleted": false,
			"id": "ktRGKOZKitfeVeRpcwo6-",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -3.647120389459559,
			"y": 900.5939943330416,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 58,
			"height": 16,
			"seed": 979407981,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "hSObC0Uq5QAcKLAqQiAMC",
					"type": "arrow"
				}
			],
			"updated": 1704980729357,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "61e294deb146f54b67ff85dc6568c861c8345551",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 179,
			"versionNonce": 1776141005,
			"isDeleted": false,
			"id": "ICGJVWXO6Wh1i1B4GurkM",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 136.40263318813768,
			"y": 897.03160663591,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 69,
			"height": 16,
			"seed": 1804435149,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "SCQW8U_Bjmyqdnw6eYq7x",
					"type": "arrow"
				}
			],
			"updated": 1704980729358,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "9c3d557e88d3610e2a4e94f9dc6c4ee36681f5ac",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "image",
			"version": 345,
			"versionNonce": 2112773251,
			"isDeleted": false,
			"id": "XPPmZyuL",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -71.3532802181985,
			"y": 996.9909818695437,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 360.73549439702214,
			"height": 49.46540224173213,
			"seed": 56411,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729358,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "875c3c4d7b7700947bb434dbeb28505f91081755",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 278,
			"versionNonce": 1679155501,
			"isDeleted": false,
			"id": "6WQyJZzB",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 317.8327077886277,
			"y": 1011.6863339832171,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 36.511962890625,
			"height": 20,
			"seed": 605994317,
			"groupIds": [
				"Cxw-F4SdjTtMrBVknF57S",
				"hjIvcZgeXcEmTC6WQidM8"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729358,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (5)",
			"rawText": "- (5)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (5)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 370,
			"versionNonce": 2143036675,
			"isDeleted": false,
			"id": "NRmxjBka",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -134.80259316136687,
			"y": 1227.2913004184675,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 455.24485206278706,
			"height": 50.44605117452506,
			"seed": 56240,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "oxp3D5ke9Y3cARg6S3VXH",
					"type": "arrow"
				},
				{
					"id": "ByoOiJH3jJ0H7_mk3WZaa",
					"type": "arrow"
				},
				{
					"id": "lHlAlweA6PB5vzqn1CrPd",
					"type": "arrow"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "1cd270cde818361ea5d83eb0490ad529bd05c1f6",
			"scale": [
				1,
				1
			]
		},
		{
			"id": "lCUtWMo4",
			"type": "text",
			"x": 63.6165350438971,
			"y": 1182.745754971232,
			"width": 22.35198974609375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 874068483,
			"version": 129,
			"versionNonce": 473697155,
			"isDeleted": false,
			"boundElements": [
				{
					"id": "oxp3D5ke9Y3cARg6S3VXH",
					"type": "arrow"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"text": "GS",
			"rawText": "GS",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "GS",
			"lineHeight": 1.25
		},
		{
			"id": "oxp3D5ke9Y3cARg6S3VXH",
			"type": "arrow",
			"x": 56.17956714638282,
			"y": 1220.9848010823143,
			"width": 12.640608857150255,
			"height": 17.239046111082416,
			"angle": 0,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"seed": 1078652941,
			"version": 274,
			"versionNonce": 1819412749,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1704980737773,
			"link": null,
			"locked": false,
			"points": [
				[
					0,
					0
				],
				[
					12.640608857150255,
					-17.239046111082416
				]
			],
			"lastCommittedPoint": null,
			"startBinding": {
				"elementId": "NRmxjBka",
				"focus": -0.2428087225985618,
				"gap": 6.306499336153138
			},
			"endBinding": {
				"elementId": "lCUtWMo4",
				"focus": -0.11310703131700764,
				"gap": 1
			},
			"startArrowhead": null,
			"endArrowhead": "arrow"
		},
		{
			"type": "text",
			"version": 147,
			"versionNonce": 732657251,
			"isDeleted": false,
			"id": "cWolS16g",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 258.36754904120426,
			"y": 1180.4823670850692,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffa94d",
			"width": 22.207992553710938,
			"height": 20,
			"seed": 1894461603,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "ByoOiJH3jJ0H7_mk3WZaa",
					"type": "arrow"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "GL",
			"rawText": "GL",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "GL",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 340,
			"versionNonce": 14870989,
			"isDeleted": false,
			"id": "ByoOiJH3jJ0H7_mk3WZaa",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 250.4226085955629,
			"y": 1218.7214131961514,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffa94d",
			"width": 12.912683324281772,
			"height": 17.23904611108219,
			"seed": 2049123395,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737773,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NRmxjBka",
				"focus": 0.5366424609896902,
				"gap": 8.569887222316083
			},
			"endBinding": {
				"elementId": "cWolS16g",
				"focus": -0.11310703131700306,
				"gap": 1
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					12.912683324281772,
					-17.23904611108219
				]
			]
		},
		{
			"type": "text",
			"version": 203,
			"versionNonce": 245124419,
			"isDeleted": false,
			"id": "WFbqY3JH",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 156.77313955238992,
			"y": 1185.5211562192048,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffa94d",
			"width": 36.49598693847656,
			"height": 20,
			"seed": 442757773,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [
				{
					"id": "lHlAlweA6PB5vzqn1CrPd",
					"type": "arrow"
				}
			],
			"updated": 1704980737638,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "GT0",
			"rawText": "GT0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "GT0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "arrow",
			"version": 499,
			"versionNonce": 698522253,
			"isDeleted": false,
			"id": "lHlAlweA6PB5vzqn1CrPd",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 155.5028224390148,
			"y": 1226.4630822159652,
			"strokeColor": "#2f9e44",
			"backgroundColor": "#ffa94d",
			"width": 16.02215545256533,
			"height": 16.131077071783693,
			"seed": 1270880493,
			"groupIds": [],
			"frameId": null,
			"roundness": {
				"type": 2
			},
			"boundElements": [],
			"updated": 1704980737773,
			"link": null,
			"locked": false,
			"startBinding": {
				"elementId": "NRmxjBka",
				"focus": 0.14567183535377098,
				"gap": 1
			},
			"endBinding": {
				"elementId": "WFbqY3JH",
				"focus": -0.39795952596007095,
				"gap": 4.8108489249766535
			},
			"lastCommittedPoint": null,
			"startArrowhead": null,
			"endArrowhead": "arrow",
			"points": [
				[
					0,
					0
				],
				[
					16.02215545256533,
					-16.131077071783693
				]
			]
		},
		{
			"id": "V3PLkYyn",
			"type": "text",
			"x": -131.71064374405842,
			"y": 843.7707430945841,
			"width": 22.35198974609375,
			"height": 20,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 1075371459,
			"version": 122,
			"versionNonce": 1728668333,
			"isDeleted": false,
			"boundElements": null,
			"updated": 1704980729358,
			"link": null,
			"locked": false,
			"text": "GS",
			"rawText": "GS",
			"fontSize": 16,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 14,
			"containerId": null,
			"originalText": "GS",
			"lineHeight": 1.25
		},
		{
			"type": "text",
			"version": 175,
			"versionNonce": 1924475555,
			"isDeleted": false,
			"id": "1hibNwpP",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 85.13621252161971,
			"y": 854.9844687769528,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"width": 36.49598693847656,
			"height": 20,
			"seed": 1891478979,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729358,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "GT0",
			"rawText": "GT0",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "GT0",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 166,
			"versionNonce": 511870221,
			"isDeleted": false,
			"id": "v1ZIQ5kO",
			"fillStyle": "solid",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 310.7172974973041,
			"y": 846.9675717792246,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffa94d",
			"width": 22.207992553710938,
			"height": 20,
			"seed": 1946630243,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980729358,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "GL",
			"rawText": "GL",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "GL",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 86,
			"versionNonce": 281336579,
			"isDeleted": false,
			"id": "BJH01scN",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 50.534867292035756,
			"y": 1116.2045826269534,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 110.04082605521634,
			"height": 22.255447966223528,
			"seed": 75509,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980785092,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "0fa511a2e86334c53716c287214466250bec1d34",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 364,
			"versionNonce": 338725869,
			"isDeleted": false,
			"id": "NTqethFo",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 193.05917795197394,
			"y": 1118.7507892654728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 36.86396789550781,
			"height": 20,
			"seed": 1658615267,
			"groupIds": [
				"-Pmn1Ln1p6fgmDRa_0-AQ",
				"2MADbyxbc9Da_Bjzh5nxE"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980798272,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (6)",
			"rawText": "- (6)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (6)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "text",
			"version": 432,
			"versionNonce": 1834210765,
			"isDeleted": false,
			"id": "k52wP6T5",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 348.85628195946833,
			"y": 1238.919558699728,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 35.231964111328125,
			"height": 20,
			"seed": 930442307,
			"groupIds": [
				"yk9krlLLBNCpyg-y_ud-6",
				"tADT9ixt3-CPif1_NcdbE"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704980808269,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (7)",
			"rawText": "- (7)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (7)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 284,
			"versionNonce": 2130774541,
			"isDeleted": false,
			"id": "V7rJ9Xp1",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -103.08619443451141,
			"y": 1686.38193273684,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 330.7343361455137,
			"height": 50.597417096888286,
			"seed": 95438,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981742857,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "06dd33beaf2ab62353615936cf4d9d3be53d0cbc",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 464,
			"versionNonce": 673643043,
			"isDeleted": false,
			"id": "eHYvI7Qy",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 257.57323960080976,
			"y": 1701.6151702977377,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 38.86396789550781,
			"height": 20,
			"seed": 516779043,
			"groupIds": [
				"lUUahGqDc5E_9v0IZLWGy",
				"LNtP1XziKEsvMk3kmSNIc"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704981760465,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (8)",
			"rawText": "- (8)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (8)",
			"lineHeight": 1.25,
			"baseline": 14
		},
		{
			"type": "image",
			"version": 416,
			"versionNonce": 316204387,
			"isDeleted": false,
			"id": "45cAYGrU",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -133.42800447673682,
			"y": 2296.26849656872,
			"strokeColor": "#000000",
			"backgroundColor": "transparent",
			"width": 344.5535510186383,
			"height": 49.56735295355849,
			"seed": 96324,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983122315,
			"link": null,
			"locked": false,
			"status": "pending",
			"fileId": "d390a398e4795073916b6ce5c33fb40ad5c7f410",
			"scale": [
				1,
				1
			]
		},
		{
			"type": "text",
			"version": 502,
			"versionNonce": 1714146125,
			"isDeleted": false,
			"id": "QWe20b6b",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": 243.98242024330693,
			"y": 2310.500945216334,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "#ffffff",
			"width": 36.36796569824219,
			"height": 20,
			"seed": 1133389699,
			"groupIds": [
				"Uxe5zCHsvbZDpvdZNZpJS",
				"mAvFGcDIk1hEKllcZrZ0Y"
			],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1704983133346,
			"link": null,
			"locked": false,
			"fontSize": 16,
			"fontFamily": 1,
			"text": "- (9)",
			"rawText": "- (9)",
			"textAlign": "left",
			"verticalAlign": "top",
			"containerId": null,
			"originalText": "- (9)",
			"lineHeight": 1.25,
			"baseline": 14
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "#ffa94d",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 1,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 16,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 541.578031316725,
		"scrollY": -1288.9288411719665,
		"zoom": {
			"value": 1.1070368002127404
		},
		"currentItemRoundness": "round",
		"gridSize": null,
		"gridColor": {
			"Bold": "#C9C9C9FF",
			"Regular": "#EDEDEDFF"
		},
		"currentStrokeOptions": null,
		"previousGridSize": null,
		"frameRendering": {
			"enabled": true,
			"clip": true,
			"name": true,
			"outline": true
		}
	},
	"files": {}
}
```
%%