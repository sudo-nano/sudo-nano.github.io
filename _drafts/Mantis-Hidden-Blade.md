---
layout: post
title: "3D Printable Mantis Hidden Blade"
date: 2024-12-01 16:00:00 -0700
tags: 3d-design 3d-printing
category: drafts
hidden: true
--- 

## Design Philosophy
> If you read recipe blogs, this is the part where I tell you my entire life story
> (slight hyperbole) before I get to the recipe. If you would rather just get on
> with building the blade, skip to section 2, printing. 
{: .prompt-tip }

### Open Source
Plenty of brilliant makers have designed their own hidden blades, but all the 
best designs 
have been kept private so that the designers can make money selling them. This 
recurring problem in the open source 3D design space, where there's a gaping
hole left by the designs people think they can monetize, frustrates me. It feels
like cherry picking the times to apply the open source ethos. Despite my 
philosophical disagreements, I can't fault creators that do this. 
At the end of the day, makers still need to put food on the table. I'm thankful
for the privilege that allows me to provide this work for free. 

### Practical Problems
I've always been a big fan of Assassin's Creed, and as a maker, I've wondered
how hard it would be to make a hidden blade. The games usually hand-wave the 
actual design of the blade, showing some rough sketches (such as those from 
Leonardo Da Vinci in Assassin's Creed II), but never anything close to a 
dimensional drawing of the mechanism. 

Building a hidden blade is something I've come back to time and time again. 
It's such an incredibly cool thing to have that the allure has never left. 
I've tried all of the free designs I could find. Among the best were the 
Dual Action OTF Hidden Blade by Stonedge
<!-- Insert thingiverse link -->
and the design by Dragon's Keep Armoury that has since been taken down. 
<!-- If I have a copy of the files somewhere, post it here -->
I was unable to complete any of them for one of three reasons: 
1. The design required extremely precise printing tolerances
2. The design required specific nonstandard parts that I couldn't find
3. Post processing required excessively fiddly techniques

For this reason, every printed part in my design is a standardized part, 
easy to fabricate from standardized parts, or has loose enough requirements
that any locally sourced substitute will work. This design was made to address
the accessibility and ease of manufacture that I feel is missing from current
open source hidden blade designs. 

This design is based on the same concept by RAWICE511 on YouTube. It promises
the ability to work underwater, since it uses a gear drive instead of an OTF
mechanism. It promises easier manufacturing because of the simpler design.
The only drawback is that the side-folding mechanism prevents you from hiding it
in a sleeve. Unfortunately, RAWICE511 never sold the mantis blade or its design
files in his shop. I thought "how hard could making this possibly be?" The 
answer was pretty hard, but not ridiculous. Many years and six blade 
iterations later, here it is.[^1]

## Printing 
### Specifications 
The most important thing about printing these parts is *minimizing warping and
elephant's foot.* All parts are designed with 0.1mm tolerances, so warped parts
will not function. 

Besides creating more work for you in post-processing, elephant’s foot can make your parts thinner if majorly squished. This can prevent the plastic sleeve bearings from fully seating into the part, which causes a variety of issues.
Depending on your printer and slicer settings, you may also have trouble with the thin parts of the holes for the sleeve bearings. It’s important that these not be underextruded, otherwise they will be very weak and prone to breaking off.

### Material 
No particular material is required for this build. Most of the development was
done with PLA. It'll work, but I really
recommend PETG to avoid warping when it gets warm outside. I had an entire assembled hidden blade go banana shaped after leaving it in the car while I got lunch.

Here are the settings I used for PLA printing: 
- **Printer:** Ender 3
- **Filament:** MatterHackers Build PLA
- **Extruder Temperature:** 200C
- **Bed Temperature:** 50C
- **Bed Material:** Coated glass
- **Enclosure:** No (I just don't have one. You can use one if you want) 
- **Bed Adhesion:** Raft

Your mileage may vary depending on the filament and printer you have. 


## Assembly 
### Tools 
The following tools are required: 
- Precision flathead screwdriver 
- Small pliers
- Clamp or stand for gluing (improvised clamps using random objects will work)
- File or sandpaper 

The following tools are recommended, but not necessary: 
- Unbent paperclip 
- M2.5 tap 
- Hobby knife 

### Parts 
The following 3D printed parts are required:: 
- Body 
- Cover 
- Bottom and top arms
- Blade
- Gear rack 

The following non 3D printed parts are required: 
|      Item            | Quantity Required | Spares Recommended |
|----------------------|-------------------|--------------------|
| Sleeve bearings      | 8                 | 4                  |
| 3mm steel dowel pins | 4                 | 2                  |
| M2.5 x 6mm screws    | 4                 | 2                  |
| \#71 extension spring | 1                | 0                 |
| Arm straps of choice | 2                 | 0                  |
| Monofilament fishing line | 1 			| 0 				|
| Superglue bottle     | 1                 | 0                  |
| Ring                 | 1                 | 0                  |

The line used to connect the ring to the mechanism must be monofilament
fishing line. Woven cord causes too much friction, so the mechanism will not
operate properly. Line with a strength greater than or equal to 10 lbs (4.5 kg)
should be used to prevent breakage. 

### Initial Assembly 
> Tapping screw holes is optional, since many 3D printed plastics are soft 
> enough to allow self-tapping as the screw is driven in. Tapping is recommended
> for plastics harder than PLA. 
{: .prompt-tip }

The arms and blade are connected to each other and the case using 4 axle 
assemblies. Each axle assembly is composed of two sleeve bearings and one dowel
pin. 

<!-- Insert diagram -->

Prepare 4 axles by gluing a dowel pin into each of 4 sleeve bearings. 



## Footnotes
[^1]: I actually finished this design several years ago, but wanted to make an instructional video on assembly before publishing. I suddenly got very busy with college, so that never happened. Now that I have a blog, I can make the instructions a living document so that I can gradually upload images, diagrams, and videos. 
