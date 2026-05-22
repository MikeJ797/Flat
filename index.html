<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>CUS Ground Floor VR - corrected Quest 3 walkthrough</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
  <meta name="description" content="Corrected Quest 3 WebXR walkthrough of the proposed CUS ground floor apartment.">
  <script src="https://aframe.io/releases/1.7.0/aframe.min.js"></script>
  <style>
    body { margin: 0; font-family: Arial, sans-serif; }
    .note { position: fixed; left: 12px; bottom: 12px; background: rgba(255,255,255,.88); padding: 10px 12px; border-radius: 8px; max-width: 540px; font-size: 13px; line-height: 1.35; z-index: 10; box-shadow: 0 2px 12px rgba(0,0,0,.12); }
    .note strong { display: block; margin-bottom: 4px; }
  </style>
  <script>
    AFRAME.registerComponent('quest-walk-controls', {
      schema: { speed: {default: 1.8}, turnSpeed: {default: 75} },
      init: function () {
        this.left = {x:0, y:0};
        this.right = {x:0, y:0};
        this.keys = {};
        this.camera = null;
        const leftHand = document.querySelector('#leftHand');
        const rightHand = document.querySelector('#rightHand');
        const setAxis = (target) => (ev) => { target.x = ev.detail.x || 0; target.y = ev.detail.y || 0; };
        const clearAxis = (target) => () => { target.x = 0; target.y = 0; };
        if (leftHand) {
          leftHand.addEventListener('thumbstickmoved', setAxis(this.left));
          leftHand.addEventListener('thumbsticktouchend', clearAxis(this.left));
        }
        if (rightHand) {
          rightHand.addEventListener('thumbstickmoved', setAxis(this.right));
          rightHand.addEventListener('thumbsticktouchend', clearAxis(this.right));
        }
        window.addEventListener('keydown', e => this.keys[e.key.toLowerCase()] = true);
        window.addEventListener('keyup', e => this.keys[e.key.toLowerCase()] = false);
      },
      tick: function (time, dt) {
        if (!dt) return;
        if (!this.camera) this.camera = document.querySelector('#camera');
        const rig = this.el.object3D;
        const cam = this.camera ? this.camera.object3D : rig;
        const seconds = Math.min(dt / 1000, 0.05);
        let moveX = this.left.x || 0;
        let moveZ = this.left.y || 0; // forward is negative in WebXR thumbstick y on most controllers
        if (this.keys['w']) moveZ = -1;
        if (this.keys['s']) moveZ = 1;
        if (this.keys['a']) moveX = -1;
        if (this.keys['d']) moveX = 1;
        // deadzone
        if (Math.abs(moveX) < 0.12) moveX = 0;
        if (Math.abs(moveZ) < 0.12) moveZ = 0;
        const yaw = cam.rotation.y;
        const sin = Math.sin(yaw), cos = Math.cos(yaw);
        // joystick y: negative means forward. Move on X/Z only so user cannot drift upward.
        const forward = -moveZ;
        const right = moveX;
        const dx = (right * cos + forward * sin) * this.data.speed * seconds;
        const dz = (-right * sin + forward * cos) * this.data.speed * seconds;
        rig.position.x += dx;
        rig.position.z -= dz;
        rig.position.y = 0; // hard floor lock: fixes floating/vertical drift
        // optional snap-ish turn from right thumbstick x
        let turn = this.right.x || 0;
        if (Math.abs(turn) > 0.30) rig.rotation.y -= turn * THREE.MathUtils.degToRad(this.data.turnSpeed) * seconds;
      }
    });

    AFRAME.registerComponent('vr-height-fix', {
      init: function () {
        const scene = this.el.sceneEl;
        const cam = document.querySelector('#camera');
        const rig = document.querySelector('#rig');
        const setVR = () => {
          if (cam) cam.setAttribute('position', '0 0 0'); // Quest local-floor supplies actual head height
          if (rig) rig.setAttribute('position', `${rig.object3D.position.x} 0 ${rig.object3D.position.z}`);
        };
        const setDesktop = () => { if (cam) cam.setAttribute('position', '0 1.6 0'); };
        scene.addEventListener('enter-vr', setVR);
        scene.addEventListener('exit-vr', setDesktop);
      }
    });

    AFRAME.registerComponent('label-toggle', {
      init: function () {
        window.addEventListener('keydown', function (ev) {
          if (ev.key.toLowerCase() === 'l') {
            document.querySelectorAll('.optional-label').forEach(el => {
              const now = el.getAttribute('visible') === true || el.getAttribute('visible') === 'true';
              el.setAttribute('visible', !now);
            });
          }
        });
      }
    });
  </script>
</head>
<body>
  <div class="note">
    <strong>Corrected Quest 3 ground-floor walkthrough</strong>
    This version resets VR height to floor level, reworks the room layout to match page 13 more closely, and keeps furniture to key scale items only. Desktop: WASD + mouse. Press L for labels/door-clearance zones.
  </div>

  <a-scene label-toggle vr-height-fix background="color: #eef1f4" renderer="antialias: true; colorManagement: true" webxr="referenceSpaceType: local-floor; optionalFeatures: bounded-floor" xr-mode-ui="XRMode: xr" shadow="type: pcfsoft">
    <a-assets>
      <img id="plan" src="assets/ground_floor_plan_page_13.png" crossorigin="anonymous">
    </a-assets>
    <a-sky color="#eef1f4"></a-sky>
    <a-entity light="type: ambient; intensity: 0.58"></a-entity>
    <a-entity light="type: directional; intensity: 0.85; castShadow: true" position="-4 6 -4"></a-entity>
    <a-entity light="type: point; intensity: 0.25; distance: 8" position="1.0 2.4 -2.0"></a-entity>

    <a-entity id="mockup-model" position="0 0 0">
      <a-plane id="site-ground" position="0 -0.012 -0.2" rotation="-90 0 0" width="18" height="16" material="color: #cbd2c1; roughness: 1"></a-plane>
      <a-box id="overall-slab"  position="0.000 0.017 0.000" width="10.610" depth="4.200" height="0.035" material="color: #e8e1d4; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bathroom-floor"  position="-4.315 0.055 -0.715" width="1.980" depth="2.770" height="0.022" material="color: #d5d7d2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="utility-floor"  position="-4.315 0.055 1.385" width="1.980" depth="1.430" height="0.022" material="color: #ddd8ce; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-floor"  position="-0.700 0.056 0.000" width="4.950" depth="4.200" height="0.020" material="color: #c3ad88; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-floor"  position="3.605 0.057 0.000" width="3.400" depth="4.200" height="0.020" material="color: #c9b38f; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-floor"  position="2.525 0.023 -4.125" width="5.560" depth="4.050" height="0.045" material="color: #cfc6b5; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="front-wall-bathroom"  position="-4.315 1.305 -2.020" width="1.980" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="front-wall-living-left-pier"  position="-2.950 1.305 -2.020" width="0.450" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="front-wall-living-centre-pier"  position="-0.915 1.305 -2.020" width="0.420" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="front-wall-living-right-pier"  position="1.600 1.305 -2.020" width="0.350" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="front-wall-bedroom-left-pier"  position="2.115 1.305 -2.020" width="0.420" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="front-wall-bedroom-right-pier"  position="5.095 1.305 -2.020" width="0.420" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="rear-wall-utility-left"  position="-4.995 1.305 2.020" width="0.620" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="rear-wall-utility-right"  position="-3.580 1.305 2.020" width="0.510" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="rear-wall-living-left"  position="-2.935 1.305 2.020" width="0.480" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="rear-wall-living-mid"  position="-0.700 1.305 2.020" width="2.350" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="rear-wall-living-right"  position="1.600 1.305 2.020" width="0.350" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="rear-wall-bedroom-mid"  position="4.080 1.305 2.020" width="2.450" depth="0.160" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="left-external-wall"  position="-5.225 1.305 0.000" width="0.160" depth="4.200" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="right-external-wall"  position="5.225 1.305 0.000" width="0.160" depth="4.200" height="2.610" material="color: #f7f5ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="service-living-wall-lower"  position="-3.250 1.305 -0.830" width="0.150" depth="2.540" height="2.610" material="color: #faf8f2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="service-living-wall-upper-short"  position="-3.250 1.305 1.710" width="0.150" depth="0.780" height="2.610" material="color: #faf8f2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bath-utility-wall-left"  position="-4.780 1.305 0.745" width="1.050" depth="0.150" height="2.610" material="color: #faf8f2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bath-utility-wall-right"  position="-3.405 1.305 0.745" width="0.160" depth="0.150" height="2.610" material="color: #faf8f2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-bedroom-wall-front"  position="1.840 1.305 -0.440" width="0.130" depth="3.320" height="2.610" material="color: #faf8f2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-bedroom-wall-rear-pier"  position="1.840 1.305 2.025" width="0.130" depth="0.150" height="2.610" material="color: #faf8f2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="utility-to-living-door-open"  position="-3.285 1.025 0.930" width="0.040" depth="0.820" height="2.050" material="color: #d5c3a8; roughness: 0.9; metalness: 0.0" rotation="0 -34 0"></a-box>
      <a-box id="bathroom-door-open"  position="-3.765 1.025 0.710" width="0.800" depth="0.040" height="2.050" material="color: #d5c3a8; roughness: 0.9; metalness: 0.0" rotation="0 34 0"></a-box>
      <a-box id="bedroom-door-open"  position="1.815 1.025 1.640" width="0.040" depth="0.780" height="2.050" material="color: #d5c3a8; roughness: 0.9; metalness: 0.0" rotation="0 -35 0"></a-box>
      <a-box id="living-front-glass-left"  position="-1.925 1.190 -2.107" width="1.600" depth="0.035" height="2.380" material="color: #a9d1e8; roughness: 0.9; metalness: 0.0; opacity: 0.38; transparent: true" ></a-box>
      <a-box id="living-front-glass-left-top-frame"  position="-1.925 2.360 -2.107" width="1.600" depth="0.055" height="0.055" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-left-bottom-frame"  position="-1.925 0.120 -2.107" width="1.600" depth="0.055" height="0.055" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-left-left-frame"  position="-2.702 1.190 -2.107" width="0.045" depth="0.055" height="2.380" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-left-right-frame"  position="-1.147 1.190 -2.107" width="0.045" depth="0.055" height="2.380" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-right"  position="0.345 1.190 -2.107" width="2.100" depth="0.035" height="2.380" material="color: #a9d1e8; roughness: 0.9; metalness: 0.0; opacity: 0.38; transparent: true" ></a-box>
      <a-box id="living-front-glass-right-top-frame"  position="0.345 2.360 -2.107" width="2.100" depth="0.055" height="0.055" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-right-bottom-frame"  position="0.345 0.120 -2.107" width="2.100" depth="0.055" height="0.055" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-right-left-frame"  position="-0.683 1.190 -2.107" width="0.045" depth="0.055" height="2.380" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-front-glass-right-right-frame"  position="1.372 1.190 -2.107" width="0.045" depth="0.055" height="2.380" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-front-glass"  position="3.605 1.190 -2.107" width="2.560" depth="0.035" height="2.380" material="color: #a9d1e8; roughness: 0.9; metalness: 0.0; opacity: 0.38; transparent: true" ></a-box>
      <a-box id="bedroom-front-glass-top-frame"  position="3.605 2.360 -2.107" width="2.560" depth="0.055" height="0.055" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-front-glass-bottom-frame"  position="3.605 0.120 -2.107" width="2.560" depth="0.055" height="0.055" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-front-glass-left-frame"  position="2.348 1.190 -2.107" width="0.045" depth="0.055" height="2.380" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-front-glass-right-frame"  position="4.863 1.190 -2.107" width="0.045" depth="0.055" height="2.380" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="utility-rear-door-frame-threshold"  position="-4.255 0.080 2.040" width="0.800" depth="0.060" height="0.035" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="living-rear-door-frame-threshold"  position="-2.255 0.080 2.040" width="0.800" depth="0.060" height="0.035" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-rear-door-frame-threshold"  position="2.415 0.080 2.040" width="0.780" depth="0.060" height="0.035" material="color: #6e553d; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-roof"  position="2.525 2.580 -4.125" width="5.560" depth="4.050" height="0.100" material="color: #f2eee5; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-roof-front-trim"  position="2.525 2.480 -6.110" width="5.560" depth="0.080" height="0.160" material="color: #d6c7ad; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-front-post-1"  position="0.145 1.260 -5.700" width="0.120" depth="0.120" height="2.520" material="color: #333333; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-front-post-2"  position="4.905 1.260 -5.700" width="0.120" depth="0.120" height="2.520" material="color: #333333; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-rear-post-1"  position="0.145 1.260 -2.480" width="0.100" depth="0.100" height="2.520" material="color: #3f3f3f; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="portico-rear-post-2"  position="4.905 1.260 -2.480" width="0.100" depth="0.100" height="2.520" material="color: #3f3f3f; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="kitchen-linear-run"  position="-2.820 0.450 -0.700" width="0.550" depth="2.100" height="0.900" material="color: #d9d3c7; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="kitchen-worktop"  position="-2.820 0.930 -0.700" width="0.610" depth="2.160" height="0.055" material="color: #53504a; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="sink"  position="-2.845 0.970 -1.205" width="0.380" depth="0.450" height="0.055" material="color: #b6b7b5; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="hob"  position="-2.845 0.980 -0.390" width="0.380" depth="0.480" height="0.035" material="color: #151515; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="fridge"  position="-2.805 0.975 0.695" width="0.580" depth="0.550" height="1.950" material="color: #e5e3df; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="central-table"  position="-0.250 0.740 0.010" width="1.250" depth="0.780" height="0.075" material="color: #745f49; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-cylinder id="central-table-leg-1"  position="-0.745 0.360 -0.240" radius="0.025" height="0.700" rotation="0 0 0" material="color: #4e4339; roughness: 0.9; metalness: 0.0" ></a-cylinder>
      <a-cylinder id="central-table-leg-2"  position="0.155 0.360 -0.240" radius="0.025" height="0.700" rotation="0 0 0" material="color: #4e4339; roughness: 0.9; metalness: 0.0" ></a-cylinder>
      <a-cylinder id="central-table-leg-3"  position="-0.745 0.360 0.220" radius="0.025" height="0.700" rotation="0 0 0" material="color: #4e4339; roughness: 0.9; metalness: 0.0" ></a-cylinder>
      <a-cylinder id="central-table-leg-4"  position="0.155 0.360 0.220" radius="0.025" height="0.700" rotation="0 0 0" material="color: #4e4339; roughness: 0.9; metalness: 0.0" ></a-cylinder>
      <a-box id="chair-1"  position="-0.835 0.270 -0.460" width="0.380" depth="0.380" height="0.420" material="color: #6f5a47; roughness: 0.9; metalness: 0.0" rotation="0 0 0"></a-box>
      <a-box id="chair-2"  position="0.135 0.270 -0.460" width="0.380" depth="0.380" height="0.420" material="color: #6f5a47; roughness: 0.9; metalness: 0.0" rotation="0 0 0"></a-box>
      <a-box id="chair-3"  position="-0.835 0.270 0.710" width="0.380" depth="0.380" height="0.420" material="color: #6f5a47; roughness: 0.9; metalness: 0.0" rotation="0 180 0"></a-box>
      <a-box id="chair-4"  position="0.135 0.270 0.710" width="0.380" depth="0.380" height="0.420" material="color: #6f5a47; roughness: 0.9; metalness: 0.0" rotation="0 180 0"></a-box>
      <a-box id="sofa-base"  position="1.105 0.270 -0.325" width="0.820" depth="1.650" height="0.340" material="color: #b8afa2; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="sofa-back"  position="1.505 0.550 -0.325" width="0.160" depth="1.650" height="0.820" material="color: #aaa194; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="coffee-table"  position="0.015 0.390 -0.520" width="0.780" depth="0.460" height="0.060" material="color: #7b644f; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bed-base"  position="3.530 0.240 -0.575" width="2.050" depth="1.550" height="0.340" material="color: #bca786; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="mattress"  position="3.530 0.520 -0.575" width="1.930" depth="1.430" height="0.180" material="color: #eee8df; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="headboard"  position="2.465 0.530 -0.575" width="0.120" depth="1.550" height="0.950" material="color: #9a8268; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bed-pillow-1"  position="2.835 0.740 -0.990" width="0.420" depth="0.380" height="0.120" material="color: #faf6ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bed-pillow-2"  position="2.835 0.740 -0.280" width="0.420" depth="0.380" height="0.120" material="color: #faf6ee; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="bedroom-wardrobe"  position="4.895 1.025 0.900" width="0.500" depth="1.100" height="2.050" material="color: #d0c7bb; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="shower-tray"  position="-4.345 0.070 -1.510" width="1.480" depth="0.780" height="0.075" material="color: #efefec; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="shower-screen"  position="-4.345 1.000 -1.123" width="1.480" depth="0.035" height="1.900" material="color: #bfe3f0; roughness: 0.9; metalness: 0.0; opacity: 0.35; transparent: true" ></a-box>
      <a-cylinder id="toilet-bowl"  position="-3.935 0.330 -0.550" radius="0.200" height="0.340" rotation="0 0 0" material="color: #f5f5f3; roughness: 0.9; metalness: 0.0" ></a-cylinder>
      <a-box id="toilet-cistern"  position="-3.915 0.780 -0.170" width="0.380" depth="0.140" height="0.380" material="color: #f3f3ef; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-box id="basin-vanity"  position="-4.810 0.390 0.210" width="0.550" depth="0.420" height="0.780" material="color: #cdc3b4; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-cylinder id="basin-bowl"  position="-4.805 0.840 0.210" radius="0.170" height="0.080" rotation="0 0 0" material="color: #f5f5f1; roughness: 0.9; metalness: 0.0" ></a-cylinder>
      <a-box id="washing-machine"  position="-4.795 0.430 1.275" width="0.580" depth="0.550" height="0.860" material="color: #eeeeeb; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-cylinder id="washing-machine-round-door"  position="-4.795 0.470 0.980" radius="0.170" height="0.035" rotation="90 0 0" material="color: #8ea1aa; roughness: 0.9; metalness: 0.0; opacity: 0.55; transparent: true" ></a-cylinder>
      <a-box id="utility-tall-storage"  position="-4.080 0.975 1.275" width="0.550" depth="0.550" height="1.950" material="color: #d0c5b5; roughness: 0.9; metalness: 0.0" ></a-box>
      <a-plane id="clearance-zone-1" class="optional-label" position="-2.875 0.063 0.900" width="0.900" height="0.900" rotation="-90 0 0" material="color: #7fb7ff; roughness: 0.9; metalness: 0.0; opacity: 0.18; transparent: true" ></a-plane>
      <a-plane id="clearance-zone-2" class="optional-label" position="2.225 0.063 1.575" width="0.900" height="0.950" rotation="-90 0 0" material="color: #7fb7ff; roughness: 0.9; metalness: 0.0; opacity: 0.18; transparent: true" ></a-plane>
      <a-plane id="clearance-zone-3" class="optional-label" position="-3.905 0.063 0.900" width="0.900" height="0.700" rotation="-90 0 0" material="color: #7fb7ff; roughness: 0.9; metalness: 0.0; opacity: 0.18; transparent: true" ></a-plane>
      <a-text id="label-bathroom" class="optional-label" visible="false" value="Bathroom / bagno
5.49 m²" position="-4.355 0.040 -0.750" rotation="-90 0 0" align="center" width="1.8" color="#1d1d1d"></a-text>
      <a-text id="label-utility" class="optional-label" visible="false" value="Utility / anti-rip
2.77 m²" position="-4.355 0.040 1.400" rotation="-90 0 0" align="center" width="1.8" color="#1d1d1d"></a-text>
      <a-text id="label-living" class="optional-label" visible="false" value="Living / soggiorno
20.14 m²" position="-0.655 0.040 1.250" rotation="-90 0 0" align="center" width="2.8" color="#1d1d1d"></a-text>
      <a-text id="label-bedroom" class="optional-label" visible="false" value="Bedroom / camera
13.42 m²" position="3.595 0.040 1.250" rotation="-90 0 0" align="center" width="2.5" color="#1d1d1d"></a-text>
      <a-text id="label-portico" class="optional-label" visible="false" value="Portico / covered porch
22.50 m²" position="2.545 0.040 -4.800" rotation="-90 0 0" align="center" width="3.0" color="#1d1d1d"></a-text>
    </a-entity>

    <!-- Original plan reference board, outside the apartment path -->
    <a-plane src="#plan" position="-6.70 1.65 3.40" rotation="0 47 0" width="3.6" height="2.7" material="side: double"></a-plane>
    <a-text value="Original proposed ground-floor plan" position="-7.76 3.16 2.33" rotation="0 47 0" width="3.1" align="center" color="#222"></a-text>

    <a-entity id="rig" quest-walk-controls="speed: 1.7; turnSpeed: 65" position="2.095 0 -4.200">
      <a-entity id="camera" camera look-controls wasd-controls="acceleration: 28" position="0 1.6 0"></a-entity>
      <a-entity id="leftHand" oculus-touch-controls="hand: left"></a-entity>
      <a-entity id="rightHand" oculus-touch-controls="hand: right"></a-entity>
    </a-entity>
  </a-scene>
</body>
</html>
