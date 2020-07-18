---
title: 3D model-viewer
abstract: Formatting with Markdown, LaTex, and Shortcodes
date: 2020-07-17
math: true
diagram: true
html: true

---

<link href="https://fonts.googleapis.com/css2?family=Roboto&family=Roboto+Slab:wght@500&display=swap" rel="stylesheet">

<link rel="stylesheet" href="demo-styles.css">

<script src="https://unpkg.com/@webcomponents/webcomponentsjs@2.1.3/webcomponents-loader.js"></script>
<script src="https://unpkg.com/intersection-observer@0.5.1/intersection-observer.js"></script>
<script src="https://unpkg.com/resize-observer-polyfill@1.5.0/dist/ResizeObserver.js"></script>
<script src="https://unpkg.com/focus-visible@5.0.2/dist/focus-visible.js" defer></script>

{{< rawhtml >}}
  <div id="card">
    <model-viewer src="third_party/TeslaCyberTruck/scene.glb"
                  alt="A 3D model of Elon Musk's Tesla Cybertruck"
                  shadow-intensity="1"
                  background-color="#FF6F59"
                  camera-controls
                  auto-rotate ar>
    </model-viewer> 
  </div>
{{< /rawhtml >}}


{{< rawhtml >}}

<model-viewer src="third_party/TeslaModel3/scene.glb"
                  alt="A 3D model of Elon Musk's Tesla Model 3"
                  shadow-intensity="1"
                  background-color="#FF6F59"
                  camera-controls
                  auto-rotate ar>
    </model-viewer>
</div>

{{< /rawhtml >}}


{{< rawhtml >}}
  <div id="card">
    <model-viewer src="third_party/XWing/model.glb"
                  alt="A 3D model"
                  shadow-intensity="1"
                  camera-controls
                  auto-rotate ar>
      </model-viewer>
  </div>
  
{{< /rawhtml >}}


{{< rawhtml >}}
  <div id="card">
<model-viewer src="third_party/Narwhal/Mesh_Narwhal.glb"
                  alt="A cute 3D model of a Narwhal"
                  shadow-intensity="1"
                  background-color="#FF6F59"
                  camera-controls
                  auto-rotate ar>
    </model-viewer>
</div>

{{< /rawhtml >}}



<script type="module"
  src="https://unpkg.com/@google/model-viewer/dist/model-viewer.js">
  </script>

  
<script nomodule
  src="https://unpkg.com/@google/model-viewer/dist/model-viewer-legacy.js">
  </script>

