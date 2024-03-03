---

excalidraw-plugin: parsed
tags: [excalidraw]

---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠==


# Text Elements
[[Algorithms & Data Structures/LeetCode Snippets/Leetcode 75#Attempt]] ^wKjgNwSo

[[Algorithms & Data Structures/LeetCode Snippets/Leetcode 75#Alt Logic]] ^5M4QjkSp

%%
# Drawing
```json
{
	"type": "excalidraw",
	"version": 2,
	"source": "https://github.com/zsviczian/obsidian-excalidraw-plugin/releases/tag/2.0.23",
	"elements": [
		{
			"id": "wKjgNwSo",
			"type": "embeddable",
			"x": 336.1729834762938,
			"y": -663.8421792630371,
			"width": 922.2928997426365,
			"height": 774.8442615643415,
			"angle": 0,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"roundness": null,
			"seed": 68730,
			"version": 424,
			"versionNonce": 116462915,
			"updated": 1709506526277,
			"isDeleted": false,
			"groupIds": [],
			"boundElements": [],
			"link": "[[Algorithms & Data Structures/LeetCode Snippets/Leetcode 75#Attempt]]",
			"locked": false,
			"scale": [
				1,
				1
			],
			"customData": {
				"mdProps": {
					"useObsidianDefaults": false,
					"backgroundMatchCanvas": false,
					"backgroundMatchElement": true,
					"backgroundColor": "#fff",
					"backgroundOpacity": 60,
					"borderMatchElement": true,
					"borderColor": "#fff",
					"borderOpacity": 0,
					"filenameVisible": false
				}
			}
		},
		{
			"type": "embeddable",
			"version": 576,
			"versionNonce": 2143961453,
			"isDeleted": false,
			"id": "5M4QjkSp",
			"fillStyle": "hachure",
			"strokeWidth": 1,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"angle": 0,
			"x": -692.9491591120586,
			"y": -611.1048449155737,
			"strokeColor": "transparent",
			"backgroundColor": "transparent",
			"width": 948.2438600620162,
			"height": 722.9423409255818,
			"seed": 248906541,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"boundElements": [],
			"updated": 1709506531543,
			"link": "[[Algorithms & Data Structures/LeetCode Snippets/Leetcode 75#Alt Logic]]",
			"locked": false,
			"customData": {
				"mdProps": {
					"useObsidianDefaults": false,
					"backgroundMatchCanvas": false,
					"backgroundMatchElement": true,
					"backgroundColor": "#fff",
					"backgroundOpacity": 60,
					"borderMatchElement": true,
					"borderColor": "#fff",
					"borderOpacity": 0,
					"filenameVisible": false
				}
			},
			"scale": [
				1,
				1
			]
		},
		{
			"id": "zxRWh0KJ",
			"type": "text",
			"x": -454.58898697124164,
			"y": 262.2654528436698,
			"width": 491.4092473528684,
			"height": 55.14220611414384,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 708361357,
			"version": 477,
			"versionNonce": 218072259,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1709506577012,
			"link": null,
			"locked": false,
			"text": "Let's simplify this problem and its solution like I'm explaining it to a child, using something familiar, like sorting colored balls.\n\nImagine you have a line of balls in front of you. These balls are only in three colors: red, white, and blue. Your job is to sort them so that all red balls come first, then all white balls, and blue balls at the end.\n\nYou have three baskets in front of you to help with sorting:\n1. The \"Red Basket\" on your left for red balls.\n2. The \"Blue Basket\" on your right for blue balls.\n3. You hold the \"Sorting Basket\" in your hands for white balls, but you don't really need to move white balls; you just leave them in the line as you find them.\n\nNow, you start from the beginning of the line with your Sorting Basket. Here's what you do:\n\n- **When you see a red ball (0):** You swap it with the ball at the position of the Red Basket because you want all red balls to be at the start. Then, you move the Red Basket one step to the right because the next red ball should go next to the one you just moved. You also move one step to the right in the line.\n  \n- **When you see a white ball (1):** You don't have to do anything with it; just move one step to the right in the line. White balls are fine where they are because you're moving red and blue balls to their correct places, which automatically sorts the white balls.\n  \n- **When you see a blue ball (2):** You swap it with the ball at the position of the Blue Basket because you want all blue balls at the end. Then, you move the Blue Basket one step to the left because the next blue ball should go next to the one you just moved. But, you don't move to the next ball in line yet because the ball you just swapped from the end could be red, and you need to check it and possibly move it to the Red Basket.\n\nYou keep doing this until you reach the Blue Basket. At that point, all balls are sorted: red balls are with the Red Basket, white balls are where they were but now correctly in the middle because you've sorted the red and blue balls around them, and blue balls are with the Blue Basket.\n\nThe key moments when you move your position in the line (the `i` index) are when you place a red ball in its correct position or when you confirm a ball is white. You don't move forward when you place a blue ball because you need to check the ball you just swapped from the end.",
			"rawText": "Let's simplify this problem and its solution like I'm explaining it to a child, using something familiar, like sorting colored balls.\n\nImagine you have a line of balls in front of you. These balls are only in three colors: red, white, and blue. Your job is to sort them so that all red balls come first, then all white balls, and blue balls at the end.\n\nYou have three baskets in front of you to help with sorting:\n1. The \"Red Basket\" on your left for red balls.\n2. The \"Blue Basket\" on your right for blue balls.\n3. You hold the \"Sorting Basket\" in your hands for white balls, but you don't really need to move white balls; you just leave them in the line as you find them.\n\nNow, you start from the beginning of the line with your Sorting Basket. Here's what you do:\n\n- **When you see a red ball (0):** You swap it with the ball at the position of the Red Basket because you want all red balls to be at the start. Then, you move the Red Basket one step to the right because the next red ball should go next to the one you just moved. You also move one step to the right in the line.\n  \n- **When you see a white ball (1):** You don't have to do anything with it; just move one step to the right in the line. White balls are fine where they are because you're moving red and blue balls to their correct places, which automatically sorts the white balls.\n  \n- **When you see a blue ball (2):** You swap it with the ball at the position of the Blue Basket because you want all blue balls at the end. Then, you move the Blue Basket one step to the left because the next blue ball should go next to the one you just moved. But, you don't move to the next ball in line yet because the ball you just swapped from the end could be red, and you need to check it and possibly move it to the Red Basket.\n\nYou keep doing this until you reach the Blue Basket. At that point, all balls are sorted: red balls are with the Red Basket, white balls are where they were but now correctly in the middle because you've sorted the red and blue balls around them, and blue balls are with the Blue Basket.\n\nThe key moments when you move your position in the line (the `i` index) are when you place a red ball in its correct position or when you confirm a ball is white. You don't move forward when you place a blue ball because you need to check the ball you just swapped from the end.",
			"fontSize": 2.205688244565755,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 53.999999999999964,
			"containerId": null,
			"originalText": "Let's simplify this problem and its solution like I'm explaining it to a child, using something familiar, like sorting colored balls.\n\nImagine you have a line of balls in front of you. These balls are only in three colors: red, white, and blue. Your job is to sort them so that all red balls come first, then all white balls, and blue balls at the end.\n\nYou have three baskets in front of you to help with sorting:\n1. The \"Red Basket\" on your left for red balls.\n2. The \"Blue Basket\" on your right for blue balls.\n3. You hold the \"Sorting Basket\" in your hands for white balls, but you don't really need to move white balls; you just leave them in the line as you find them.\n\nNow, you start from the beginning of the line with your Sorting Basket. Here's what you do:\n\n- **When you see a red ball (0):** You swap it with the ball at the position of the Red Basket because you want all red balls to be at the start. Then, you move the Red Basket one step to the right because the next red ball should go next to the one you just moved. You also move one step to the right in the line.\n  \n- **When you see a white ball (1):** You don't have to do anything with it; just move one step to the right in the line. White balls are fine where they are because you're moving red and blue balls to their correct places, which automatically sorts the white balls.\n  \n- **When you see a blue ball (2):** You swap it with the ball at the position of the Blue Basket because you want all blue balls at the end. Then, you move the Blue Basket one step to the left because the next blue ball should go next to the one you just moved. But, you don't move to the next ball in line yet because the ball you just swapped from the end could be red, and you need to check it and possibly move it to the Red Basket.\n\nYou keep doing this until you reach the Blue Basket. At that point, all balls are sorted: red balls are with the Red Basket, white balls are where they were but now correctly in the middle because you've sorted the red and blue balls around them, and blue balls are with the Blue Basket.\n\nThe key moments when you move your position in the line (the `i` index) are when you place a red ball in its correct position or when you confirm a ball is white. You don't move forward when you place a blue ball because you need to check the ball you just swapped from the end.",
			"lineHeight": 1.25
		},
		{
			"id": "jp8b0YAV",
			"type": "text",
			"x": -149.4812249821091,
			"y": 328.30000002070665,
			"width": 9.999984741210938,
			"height": 25,
			"angle": 0,
			"strokeColor": "#1e1e1e",
			"backgroundColor": "transparent",
			"fillStyle": "solid",
			"strokeWidth": 2,
			"strokeStyle": "solid",
			"roughness": 1,
			"opacity": 100,
			"groupIds": [],
			"frameId": null,
			"roundness": null,
			"seed": 2118515565,
			"version": 2,
			"versionNonce": 704104835,
			"isDeleted": true,
			"boundElements": null,
			"updated": 1709506573462,
			"link": null,
			"locked": false,
			"text": "",
			"rawText": "",
			"fontSize": 20,
			"fontFamily": 1,
			"textAlign": "left",
			"verticalAlign": "top",
			"baseline": 18,
			"containerId": null,
			"originalText": "",
			"lineHeight": 1.25
		}
	],
	"appState": {
		"theme": "light",
		"viewBackgroundColor": "#ffffff",
		"currentItemStrokeColor": "#1e1e1e",
		"currentItemBackgroundColor": "transparent",
		"currentItemFillStyle": "solid",
		"currentItemStrokeWidth": 2,
		"currentItemStrokeStyle": "solid",
		"currentItemRoughness": 1,
		"currentItemOpacity": 100,
		"currentItemFontFamily": 1,
		"currentItemFontSize": 20,
		"currentItemTextAlign": "left",
		"currentItemStartArrowhead": null,
		"currentItemEndArrowhead": "arrow",
		"scrollX": 1781.8175057604253,
		"scrollY": 702.9284453609946,
		"zoom": {
			"value": 0.497752827997299
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