---
title: FOV calculator
layout: default
mathjax: true
permalink: /fov
---

## Finding focal value

<center>
<img src="/assets/imgs/focal.svg" style="max-width:250px" />
</center>

<div class="alert alert-info">
If you are not sure about your camera, you can use the following form to estimate its focal value.
Simply use your camera in capture mode, facing a plane (e.g. the floor or a wall), and measure the distance from the camera to the plane, as well as the size of the diagonal of the image on the plane. Use 1920x1080 resolution.
</div>

<form id="camera">
    <div class="form-group">
        <label for="camera-distance">Camera distance to the plane (m)</label>
        <input type="text" class="form-control" id="camera-distance" />
    </div>
    <div class="form-group">
        <label for="diagonal-size">Size of the diagonal, in 1080p (m)</label>
        <input type="text" class="form-control" id="diagonal-size" />
    </div>
    <input type="submit" class="btn btn-primary form-control m-1" value="Update" />
</form>

<div class="alert alert-success">

<h2>focal value</h2>

<form>
    <div class="form-group">
        <label for="focal-value">
        Here is the focal value, to use in the Game Controller configuration:
        </label>
        <input type="number" class="border-success form-control" id="focal-value" placeholder="Enter focal length" value="885" />
    </div>
</form>

</div>

## Camera field of view

Assuming an image with a 1920x1080 aspect ratio, the following are the field of view angles for the camera:

<ul>
    <li>
        <b>Width FOV:</b> <span class="widthFOV"></span>°
    </li>
    <li>
        <b>Height FOV:</b> <span class="heightFOV"></span>°
    </li>
    <li>
        <b>Diagonal FOV:</b> <span class="diagonalFOV"></span>°
    </li>
</ul>

Mounted at a height of 2m, the camera will see the following field dimensions:

<ul>
    <li class="length-2m">
        <b>Length at 2m:</b> <span class="lengthAt2m"></span> m
    </li>
    <li class="width-2m">
        <b>Width at 2m:</b> <span class="widthAt2m"></span> m
    </li>
</ul>

## Seeing the field

To see the whole field, the camera should be placed at a minimum height of <span class="cameraHeight"></span> m.

<div class="alert alert-danger camera-height-alert">
    The proposed setup has a mount point of 2.0m. If the camera height is higher, you may need to adjust the mount point.
</div>

<script>
    document.querySelector('form#camera').addEventListener('submit', function(e) {
        e.preventDefault();
        const diagonalPixels = Math.sqrt(1920**2 + 1080**2);
        const cameraDistance = document.querySelector('#camera-distance').value;
        const diagonalSize = document.querySelector('#diagonal-size').value;


        const focalValue = (diagonalPixels * cameraDistance) / diagonalSize;
        document.querySelector('#focal-value').value = focalValue.toFixed(0);
        updateFOV();
    });

    function computeFOV(focal, pixels) {
        return 2 * Math.atan(pixels / (2 * focal)) * 180 / Math.PI;
    }

    function updateFOV()
    {
        const focalValue = document.querySelector('#focal-value').value;
        document.querySelector(".widthFOV").textContent = computeFOV(focalValue, 1920).toFixed(2);
        document.querySelector(".heightFOV").textContent = computeFOV(focalValue, 1080).toFixed(2);
        document.querySelector(".diagonalFOV").textContent = computeFOV(focalValue, Math.sqrt(1920**2 + 1080**2)).toFixed(2);

        const fieldLength = 2.45;
        const fieldWidth = 1.84;

        const lengthAt2m = (1920 / focalValue) * 2;
        const widthAt2m = (1080 / focalValue) * 2;
        document.querySelector(".lengthAt2m").textContent = lengthAt2m.toFixed(2);
        document.querySelector(".widthAt2m").textContent = widthAt2m.toFixed(2);
        if (fieldLength > lengthAt2m) {
            document.querySelector('.length-2m').classList.add('text-danger');
        } else {
            document.querySelector('.length-2m').classList.remove('text-danger');
        }
        if (fieldWidth > widthAt2m) {
            document.querySelector('.width-2m').classList.add('text-danger');
        } else {
            document.querySelector('.width-2m').classList.remove('text-danger');
        }
        
        const cameraHeightLength = (focalValue / 1920) * fieldLength;
        const cameraHeightWidth = (focalValue / 1080) * fieldWidth;
        const cameraHeight = Math.max(cameraHeightLength, cameraHeightWidth);
        document.querySelector(".cameraHeight").textContent = cameraHeight.toFixed(2);

        if (cameraHeight > 2.0) {
            document.querySelector('.camera-height-alert').classList.remove('d-none');
        } else {
            document.querySelector('.camera-height-alert').classList.add('d-none');
        }
    }

    document.querySelector('#focal-value').addEventListener('keyup', updateFOV);
    document.querySelector('#focal-value').addEventListener('change', updateFOV);
    updateFOV();
</script>