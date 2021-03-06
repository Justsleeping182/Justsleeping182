<html>
    <head>
        <title>Door test</title>
    </head>
    <body>
	<model-viewer id="reveal" interaction-prompt="none" autoplay loading="eager" ios-src="./assets/scene.usdz#applePayButtonType=buy&checkoutTitle=Wooden%20Door&checkoutSubtitle=Rustic%20finish&price=$150" src="./assets/scene.gltf" ar ar-modes="webxr scene-viewer quick-look" ar-scale="auto" camera-controls alt="A 3D model of a door">
		<button slot="ar-button" style="width:25%; height: 15vh; font-size:40px; background-color: white; border-radius: 4px; border: none; position: absolute; top: 32px; right: 32px; background-image: url(./assets/ic_view_in_ar_new_googblue_48dp.png)">
			Activate AR
		</button>
	</model-viewer>    
	<div class="slider">
		<div class="slides">
		</div>
	</div>
	<script type="module">
	  const modelViewer = document.querySelector("model-viewer");

	  function sleep(ms) {
	    return new Promise(resolve => setTimeout(resolve, ms));
	  }
		
	  window.switchSrc = (element, name) => {
	    const base = "./assets/" + name + "/" + name;
	    modelViewer.src = base + '.gltf';
	    //modelViewer.iossrce = base + '.usdz';
	    const slides = document.querySelectorAll(".slide");
	    slides.forEach((element) => {element.classList.remove("selected");});
	    element.classList.add("selected");
	    console.log(modelViewer.animationName);
	    modelViewer.play();
	  };

	
	</script>

	<style>
	  /* This keeps child nodes hidden while the element loads */
	  :not(:defined) > * {
	    display: none;
	  }

	  model-viewer {
	    background-color: #222222;
	    --poster-color: #eee;
	    width:100%;
	    height:100vh;
	  }

	  model-viewer#reveal {
	    --poster-color: transparent;
	  }
		
	  #ar-button {
	    background-image: url(./assets/ic_view_in_ar_new_googblue_48dp.png);
	    background-repeat: no-repeat;
	    background-size: 20px 20px;
	    background-position: 12px 50%;
	    background-color: #fff;
	    position: absolute;
	    left: 50%;
	    transform: translateX(-50%);
	    white-space: nowrap;
	    bottom: 132px;
	    padding: 0px 16px 0px 40px;
	    font-family: Roboto Regular, Helvetica Neue, sans-serif;
		font-size:40px;
	    color:#4285f4;
	    line-height: 36px;
	    border-radius: 18px;
	    border: 1px solid #DADCE0;
	  }

	  #ar-button:active {
	    background-color: #E8EAED;
	  }

	  #ar-button:focus {
	    outline: none;
	  }

	  #ar-button:focus-visible {
	    outline: 1px solid #4285f4;
	  }

	  @keyframes circle {
	    from { transform: translateX(-50%) rotate(0deg) translateX(50px) rotate(0deg); }
	    to   { transform: translateX(-50%) rotate(360deg) translateX(50px) rotate(-360deg); }
	  }

	  @keyframes elongate {
	    from { transform: translateX(100px); }
	    to   { transform: translateX(-100px); }
	  }



	  .slider {
	    width: 100%;
	    text-align: center;
	    overflow: hidden;
	    position: absolute;
	    bottom: 16px;
	  }

	  .slides {
	    display: flex;
	    overflow-x: auto;
	    scroll-snap-type: x mandatory;
	    scroll-behavior: smooth;
	    -webkit-overflow-scrolling: touch;
	  }

	  .slide {
	    scroll-snap-align: start;
	    flex-shrink: 0;
	    width: 100px;
	    height: 100px;
	    background-size: contain;
	    background-repeat: no-repeat;
	    background-position: center;
	    background-color: #fff;
	    margin-right: 10px;
	    border-radius: 10px;
	    border: none;
	    display: flex;
	  }

	  .slide.selected {
	    border: 2px solid #4285f4;
	  }

	  .slide:focus {
	    outline: none;
	  }

	  .slide:focus-visible {
	    outline: 1px solid #4285f4;
	  }

	</style>
	<!-- Import the component -->
	<script type="module" src="https://unpkg.com/@google/model-viewer/dist/model-viewer.min.js"></script>
	<script nomodule src="https://unpkg.com/@google/model-viewer/dist/model-viewer-legacy.js"></script>
    </body>
</html>
