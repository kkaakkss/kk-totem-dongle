#keymap drawer 그리기 :

  ##아래 경로에 YAML추가
  ```경로 : 
  .github/workflows/draw-keymaps.yml
  ```
  
  내용 
  ```YAML
  name: Draw ZMK keymap
  
  on:
    workflow_dispatch:
    push:
      paths:
        - "config/*.keymap"
        - "config/info.json"
        - "keymap_drawer.config.yaml"
  
  jobs:
    draw:
      uses: caksoylar/keymap-drawer/.github/workflows/draw-zmk.yml@main
      permissions:
        contents: write
      with:
        keymap_patterns: "config/*.keymap"
        output_folder: "keymap-drawer"
        draw_args: "totem:'-j config/info.json -l LAYOUT'"
  ```


---

![Uploading TOTEM_logo_bright.svg…]()
