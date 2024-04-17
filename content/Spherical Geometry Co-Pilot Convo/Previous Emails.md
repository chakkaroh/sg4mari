On Fri, Apr 5, 2024 at 2:26 AM coconut talkies <[coconuttalkies@gmail.com](mailto:coconuttalkies@gmail.com)> wrote:  

> Dear CP,
> 
>   
> 
> I hope this message finds you well. My name is Rohan Muraleedharan and I am an independent filmmaker based in Kerala, India. I am currently working on a film project (not yet titled) and I am reaching out to you because I greatly admire your YouTube channel which has been a source of inspiration and excitement. The mind-bending worlds that you create are playgrounds for creativity and I've been imagining using them to elicit an emotional reaction would be absolutely amazing. With the current project I'm working on, such an opportunity has arisen. I believe that your expertise could greatly benefit our project and hopefully be an exciting adventure for you as well.
> 
>   
> 
> Our film is about a boy called "A" whose personal diary is read by strange people and creatures who accuse him of things he may or may not have written and of things he may or may not do. Through this, we are aiming to explore themes of identity, and morality, and how a lack of privacy can shatter both. The interventions that he faces escalate one after the other and the last one is at a point where even the laws of physics do not function as they should. For this I envision the rules of the world you showcased in [Spherical Geometry Is Stranger Than Hyperbolic - Hyperbolica Devlog #2](https://youtu.be/yY9GAyJtuJ0?si=6HK_OZ0ZdKOePBCk) would be perfect. There is no running away from anything or anyone, if you run away to the maximum distance away from it it'll be looming over your head inside out. Try to run away from that, you'll be running closer to it. 
> 
>   
> 
> I believe that your knowledge of creating these worlds would add a great deal of value to our project, and I am confident that our collaboration would result in a truly original film.
> 
>   
> 
> I understand that you are likely very busy, so I appreciate any amount of time or resources you might be able to contribute. Whether it's working on crafting the visuals or even just pointing us in the right direction, any help would be greatly appreciated.
> 
>   
> 
> If you are interested in this opportunity, I would be more than happy to arrange a meeting at your earliest convenience to discuss this further. Please let me know if there is a specific time that works best for you. 
> 
>   
> 
> Thank you for considering my proposal. I look forward to potentially working with you and creating something truly special.
> 
>   
> 
> Best regards,
> 
>   
> 
> Rohan Muraleedharan
> 
>   
> 
> PS: Here is a link to our YouTube channel [Coconut Talkies](https://www.youtube.com/@coconuttalkies) if you want to check out our previous works.

On Sun, Apr 7, 2024 at 10:08 AM Code Parade <[codeparade.email@gmail.com](mailto:codeparade.email@gmail.com)> wrote:  
> 
> > Hi Rohan,
> > 
> >   
> > 
> > Thanks for reaching out.  Yes, I am busy at the moment but I could walk you through the technical steps of how to do the effect in practice.  It would likely require some amount of CG or environment scans to do the effect accurately.
> > 
> >   
> > 
> > Cheers!
> > 
> > -Kevin

On Thu, Apr 11, 2024 at 4:15 AM coconut talkies [coconuttalkies@gmail.com](mailto:coconuttalkies@gmail.com) wrote:  

> Hello Kevin,
> 
>   
> 
> Thank you for the prompt response! I appreciate your offer and would like to go ahead with this. As you mentioned, the technical steps of how to bring this effect together are something we're puzzled by and the rendering of the non-euclidian nature of the world is the big obstacle I'm stuck at right now. My 3D software of choice is usually Blender and I couldn't find much about recreating this in it, at least with the level of knowledge of the software I have. So it would be great if you could walk me through the steps so that I can create a sort of pipeline for this project.  
>   
> 
> Have a great day!  
> 
> Rohan Muraleedharan

From: Code Parade <codeparade.email@gmail.com>
Date: Fri, 12 Apr 2024, 12:32 am
Subject: Re: Spherical Geometry in cinema
To: coconut talkies <coconuttalkies@gmail.com>

>So what you would need to do is have 6 environment scans that each represent 1 cube of the world (like how a square would be 1 box of a cube).  Then in blender you would add each one with a different mobius transformation, or stereographic projection.  You can definitely do this with Blender's geometry nodes.  I can give you the specific formulas and parameters if you'd like, but I think it will take a bit of effort to get working.
>
>-Kevin

On Sun, Apr 14, 2024 at 2:47 AM coconut talkies <[coconuttalkies@gmail.com](mailto:coconuttalkies@gmail.com)> wrote:  

> Hello Kevin!
> 
> I have some questions and thoughts:
> 
>   
> 
> 1. Environment Scans: When referring to environment scans, could you please specify whether you are indicating HDRIs, photo scans, or another method entirely? My presumption is that if it involves an HDRI, one would utilize a single HDRI six times, corresponding to the actual set required. However, if this understanding is incorrect, could you kindly define what 'scan' signifies in this scenario?
> 
> 2. Geometry Nodes: The concept of applying distinct Möbius transformations or stereographic projections within Blender was somewhat perplexing. We contemplated executing a stereographic projection from within the HDRI onto a cube's face, repeating this for all six faces to achieve spherical space. Could you elaborate on this process within the context of Blender?
> 
> 3. Spherical Space: For an authentic spherical space, we assume the environmental alterations should be camera-dependent, with corresponding projection adjustments. This led us to infer that "environment scans" might not refer to HDRIs but rather to scans incorporating mesh data. Could you clarify the nature of these scans and the appropriate method for capturing them if the setting was a square room containing a table and a chair?
> 
>   
> 
> All these doubts arise from the fact that we're not well versed in this arena of Blender and we hope you would be forgiving on that account haha :)







