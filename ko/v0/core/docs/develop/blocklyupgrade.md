# Blockly Upgrade

In order to update blockly to the latest version, follow the following steps to make sure our extensions of blockly still work.

This should be done across different browsers to ensure browser compat.

## 업데이트

Check out the latest version of blockly from the following repo:

<https://github.com/google/blockly>

## 테스팅

Test the following on various browsers:

### 블록/코드 크기 확대 및 축소

* Use the mouse to scroll in / out. 
* Ctrl / Cmd + 마우스스크롤 조합을 이용해 크기를 조절할 수 있습니다. 

### 도구 상자

* Able to select different categories and drag various blocks into the workspace. 
* Select a category that has a "More..." subcategory
* Select the parent category and switch between them back and forth 
* Select the parent category, then select it again to hide it. 
* Select any category, and select it again to hide it. 
* Select the Advanced category to toggle advanced categories, and select it again to hide them. 

### Help Card

* Select any block, from the toolbox and the workspace. A help card should appear. Select it again, it should stay there. 
* Click on a help card, and make sure you can browse to it's help resources. 
* Click anywhere in the workspace, make sure the help card disappears. 

### Typing a string

* Select a block that inputs a string, and type in the string.

### Resize workspace

* Resize the window, and make sure Blockly auto-sizes to fit the window.
* Check what that looks like in a mobile view. 

### 오른쪽 클릭 메뉴

* Right click anywhere in the workspace, make sure our custom context menu appears with options to Delete, Shuffle and Download a screenshot. 
* Check that downloading a screenshot works. 
* Check that deleting / shuffling works. 

### Javascript editor

* Make sure you can switch to the Javascript editor and back and forth between the two editors.

### Sandbox Mode

* Check sandbox mode for both the blocks editor and the Javascript editor. 

### Custom Variables Flyout

* Check that the custom variables flyout looks right, and that you're able to create, delete, and change variables from within Blockly.