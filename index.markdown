---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
list_title: Meetups
---

<center>
  <canvas id="glcanvas" width="500px" height="500px" tabindex="1"></canvas>
</center>

<script type="text/javascript" src="cables_sketches/pott/patch.js" async></script>


<script type="text/javascript">

    function showError(errId, errMsg)
    {
        // handle critical errors here if needed
    }

    function patchInitialized(patch)
    {
        // You can now access the patch object (patch), register variable watchers and so on
    }

    function patchFinishedLoading(patch)
    {
        // The patch is ready now, all assets have been loaded
    }

    document.addEventListener("CABLES.jsLoaded", function (event)
    {
        CABLES.patch = new CABLES.Patch({
            patch: CABLES.exportedPatch,
            "prefixAssetPath": "",
            "assetPath": "",
            "jsPath": "",
            "glCanvasId": "glcanvas",
            "glCanvasResizeToWindow": false,
            "onError": showError,
            "onPatchLoaded": patchInitialized,
            "onFinishedLoading": patchFinishedLoading,
            "canvas": {"alpha":true, "premultipliedAlpha":true } // make canvas transparent
        });
    });

    // disable rubberband effect on mobile devices
    document.getElementById('glcanvas').addEventListener('touchmove', (e)=>{ e.preventDefault(); }, false);
</script>