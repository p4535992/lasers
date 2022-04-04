# lasers - light-beams and mirrors
FoundryVTT module for lasers, or light-beams that can be reflected using mirrors. This preliminary beta version implements mirrrors and light sources that interact with each other.
Both the mirrors and lightsources are tokens, and they are thus compatible with pushable tokens.

## Help:
 * Create a token that has the image of your desired light source. The image must be rotated so that the light comes out in the down direction. 
 * Edit the token (1), and in the configuration click the leftmost of the two checkboxes (2), to indicate that this is your light.
 * In the light settings of your lamp, style your lightsource to your heart's desire. Remember to set the Emission Angle to a narrow ray, e.g., 5 Degrees.
 * Create another token, and choose an image of a mirror. The reflecting side should also point downward.
 * Edit the token (1), and select the middle checkbox (3), denoting this as a mirror.
 * Rotate tokens, to your desired position, or better yet, install Monks Active tiles, and create buttons that your players can interact with.

![image](https://user-images.githubusercontent.com/8543541/160940062-3a61394f-8ac1-4026-8e23-42394705bbd9.png)

![image](https://user-images.githubusercontent.com/8543541/161455679-06a1a352-256b-4415-81a1-d44f859087f5.png)


The players does not need to have permissions to any of the tokens. If you install ["pushable"](https://github.com/oOve/pushable) tokens your players can push the mirrors or light-sources around.

The light tokens will create multiple extra light tokens that act as each reflection. It can happen that the light looses them instead of deleting them automatically. If they do, you can manually select and delete them. The image for the reflecting light token is 💢. If you wish to change this default image, you'l find it in the module's folder under media.

All tokens have a field next to the sensor checkbox that enables you to enter the name of a macro. This macro will be called every time the number of lights change on this sensor. Below is a example macro that prints out some information.
```JS
console.warn(token);
let activelights = token.document.getFlag('lasers', 'active_lights');
console.log(activelights);
if (activelights.length>0){
  // Do something exciting
  console.log("Exciting things here!");
}
```

Both the light source and the mirrors create a small wall behind them. This wall will be rotated and moved along with the token (and deleted when the token is deleted). It may happen that these walls are left behind, in that case, manually delete them.

## TODO:
 * Implement support for Monks Active tiles, so that light beams can trigger them. As far as today, there is no interaction outside this module of the light-beams. 
 * Colored lights, and the possibility for filters, that change the color of the light along its path.
 * Probably bug-fixing


Do you like this module?; then please support me at [Patreon](https://www.patreon.com/drO_o).

Would you like to show off your creations or ask questions about the module feel free to drop in at my [discord channel](https://discord.gg/5CCAhsKFDp). 
