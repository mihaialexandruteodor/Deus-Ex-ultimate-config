from [this steam tutorial](https://steamcommunity.com/sharedfiles/filedetails/?id=2967089130)
and [this answer](https://www.reddit.com/r/linux_gaming/comments/1fleuqw/comment/lo3zod9/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

# TL;DR 
Step 1 – Launch Deus Ex once with Proton

In Steam, right-click Deus Ex: Game of the Year Edition → Properties → Compatibility.

Check “Force the use of a specific Steam Play compatibility tool”.

Pick Proton Experimental (or your preferred Proton build).

Launch the game, let it reach the menu, then quit.

Step 2:

put the Kentie files  in the System folder but first install via protontricks with:

```
protontricks 6910 d3dx10 vcrun2010 dxvk

```

then launch from Steam as non steam game weith compatibility mode proton experimental

## For me the custom launcher didn't work with direct3d 10 but launching the regular game and checking 'show all rendering options' on popup at first run allowed me to check direct3d 10 rendering 

