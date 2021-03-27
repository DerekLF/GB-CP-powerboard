# Gameboy Color&Pocket powerboard
## What is it and what have you done with it?
easy easy. It's a replacement power board for the Gameboy Color and Gameboy Pocket.

## Why would you make such a thing?
Well.. to be honest, it started as a simple project to replace the power board of one of my dead Gameboy Colors. But when I developing the board I noticed that the Gameboy Pocket has the exact same power board, or atleast almost the same. It doesn't have the 13.6v power rail used by the GBc to drive it's multicolor TFT LCD.
So I made it to work with both the Pocket and Color.
And now for the real reason I made it, because there simple aren't any replacement boards on the market at the moment. Most of us retrohobbyists prefer to just smack in a pre-built board instead of going through the hassle of soldering all these tiny parts.

## Then what did you try to achieve by doing this?
The main goal of this project was for me to finally finish a project, those who are reading this and are aware of my current progress with other projects are probably laughing out loud at the moment. 
But I always kept in mind; It should be simple, it should work good and not cost too much.

## How the hell does it work?
The general idea is simple, convert a lower voltage to a higher voltage. Then a couple of solutions come to mind; Flyback, charge pump and boost converter. While the first one would've probably saved us some parts and it is how the original boards work it's also the most expensive option. As the transformer alone costs roughly the same as the parts needed for both the charge pump and boost converter. I eventually choose for a boost converter simple because of the load current, charge pumps arent exactly realiable which such variang load currents. 
![Basic boost converter](https://user-images.githubusercontent.com/39482719/112718951-7e7aad00-8ef6-11eb-822b-6a4f41e78da9.png)
Theory of operation and well since I'm not getting paid for this so I wont explain how this works. So for now some 'magic' happens, and poof we've got 5v.

So now we can convert any input voltage less then the output voltage to the output voltage, simple right. And that was the hardest part, ow wait no..
We still have the 2 remaining power rails of 13.6v and -15v. Voltage inverters are a thing nowadays, but they're expensive or impossible to find(or in those weird SOP-8 packages). Looking back the different regulator options we have, one does stand out a bit. High voltage and low current hmm? A charge pump it is. But.. Those ICs are also very expensive. But what if we combine several methods. Like the boost-convert and charge-pump.
![Boost+Charge pump circuit](https://user-images.githubusercontent.com/39482719/112719217-14fb9e00-8ef8-11eb-8637-2ad4daf0973e.png)
Et voila. We're done, we've got our high positive negative voltage rail.
Ideally the negative output voltages formula would be like Vneg=(Vpos-2xVf)x-1. But this depends on the load current of both the Vpos as the Vneg.

## Installation
This is pretty straight forward, solder the jumper depending on which gameboy it is for. Remove the original board, leave the original pins standing. Solder the board on the pins, attach the battery and VBUS wires. Check wiring and light 'em up. 
For more information regarding the installation of the board, see the instruction paper that's you've received with the board. Or view it [here](https://github.com/DerekLF/GB-CP-powerboard/blob/main/Installation%20instruction%20V1.2a.png).
_insert installation video_

## FAQ
<!-- Question 1, Where can I buy the boards?-->
<details closed>
<summary>Where can I buy the boards?</summary>
<br>
You can buy the boards on our Tindie store or on the shop.insidegadgets.com <br/>
Tindie is for Europe only, while shop.insidegadgets.com is for the rest of the world <br/>
</details>

<!-- Question 2, Can I make my own board?-->
<details closed>
<summary>Can I make my own board?</summary>
<br>
Sure you can, all you need to know and what I'll tell you is explained above.  <br/>
Will I be happy with you copying my work? Nope.  <br/>
Will I offer help in creating your own version? Nope.  <br/>
If you fry something with you own version of the board, can I be held responsible? Lol, no but I will laugh for a good minute or 2.  <br/>
</details>

<!-- Question 3, HELP!! Why doesnt my board work?-->
<details closed>
<summary>HELP!! Why doesnt my board work?</summary>
<br>
That is a very good question, it can depend on quiet a lot of factors. Here are some methods you can try to resolve the issue:  <br/>
  1. Check wiring, if something isn't wired correctly it will obviously not work  <br/>
  2. If you can check if all voltages are within the given limits.  <br/>
  3. Remove the batteries, flick the switch to "ON" and measure contuinity between VIN and the BAT+ terminal. This should be <*??*Ohm. If the contuinity is higher then *??*Ohms its a bad solder job. If there is no contuinity it might be a blown fuse.  <br/>
  4. 
</details>

## Feature request
If you have any feature request just open an issue and state what you want to see changed or explain your idea. If I like it and it's doable I might send you a reward free of charge.
If you have a wicked idea for a new mod or want to have something developed to make your life easier just contact me on _459647@student.fontys.nl_ and we can probably work something out
## Contact
You can find me in the various Gameboy related discord server, but my main base of operation is located in the InsideGadgets Discord server.
