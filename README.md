# Lava Lamp Simulator <img src="volcano.png" style="float:right" align="right" >

A relaxing lava lamp simulator using WebGL, with simple controls. Based on [Alfons Nilsson](https://codepen.io/TC5550)'s [Metaballs](https://codepen.io/TC5550/pen/WNNWoaO).

<a href="https://jimmckeeth.github.io/lavalamp/"><img  alt="lava lamp simulator" src="https://github.com/user-attachments/assets/c85a1b30-08dd-4f30-b483-832673a1ae65" /></a>

Updated to use [cryptographically secure random numbers](https://developer.mozilla.org/en-US/docs/Web/API/Crypto/getRandomValues), to provide the same entropy as [Cloudflare's wall of entropy](https://www.cloudflare.com/learning/ssl/lava-lamp-encryption/).

```JavaScript
function moreRandom() {
  const array = new Uint32Array(1);
  crypto.getRandomValues(array);

  // Divide by the maximum 
  //   32-bit unsigned integer + 1 
  //   to get a range of [0, 1)
  return array[0] / (0xFFFFFFFF + 1);
}
```

Why? *Why not?*
