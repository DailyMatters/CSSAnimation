# A Crash Course on CSS3 Animations

Animation has been one of the pillars of interactivity on the internet. Be it films, animated gifs, flash animation, you name it. When used correctly, animation is one of the most powerful interactivity tools, it brings life to the screen and adds a whole new layer of of user experience.

But I'm not here to talk about the history of animation on the internet or the complexity of user experience using animation. I'm here to talk to you about using CSS3 to animate elements on your webpage.

Animations in CSS are like transitions on steroids! Instead of an initial and final state, with animations you are allowed to use different intermediate states that will create more complex and sophisticated animations.
The fact that is simpler to write than an animation in Javascript makes it perfect for small animations. Summing up, they're very powerful, yet simple to use and fast to create, this is because the animation is handled by the browser, 
and not by your code.

The main component of an animation is CSS is **@keyframes**. **@keyframes** is the CSS rule where the animation is created. The **@keyframes** component is composed of 3 main properties.

* The name of the animation
* The stages of the animation from 0% to 100% (or using the to and from keywords which correspond to 0% and 100% respectively)
* CSS styles. This styles represent the element at each stage of the animation.
	
For example let's consider our little friend, the red little square:

```html
<html>
    <head>
        <style> 
        div {
            width: 100px;
            height: 100px;
            background-color: red;
        }
        </style>
    </head>
    <body>
        <div></div>
    </body>
</html>
```

Our goal is to create an animation that will change the color of our little red square. Using the notation we saw earlier it would look like this:

```css
@keyframes example {
    0% {background-color: red;}
    100% {background-color: yellow;}
}
```
or the equivalent:

```css
@keyframes example {
    from {background-color: red;}
    to {background-color: yellow;}
}
```

Now that we have our animation defined, we need to call it inside the CSS selector we want to animate. To do that we use the **animation** property. The **animation** property can have multiple properties:

* **animation-name**: @keyframes animation name
* **animation-duration**: the timeframe length
* **animation-timing-function**: the animation speed
* **animation-delay**: the time before the animation starts
* **animation-iteration-count**: how many times will the animation play
* **animation-direction**: gives the ability to change the loop direction ( backwards for example )
	
Given this information, let's complete our little red square animation. When all is said and done, our little red square will become our little yellow square! 
To complete the animation let's add the following 2 lines to our div:

```css
div {
    width: 100px;
    height: 100px;
    background-color: red;
    animation-name: example;
    animation-duration: 4s;
    }
```
	
We are explicitly telling that the animation ( @keyframes ) to use is the one called 'example', and that the animation will take 4 seconds.

Having an animation with only 2 states it's just like having a transition. So let's add another state so you can see the power of the animation. 
Let's say that in between going from red to yellow we want our little square to be green. To do that we'll add a 50% state, just like this:

```css
@keyframes example {
    0% {background-color: red;}
    50% {background-color: green;}
    100% {background-color: yellow;}
}
```

As you can see, now we're transitioning from red to green to yellow. The more states we add the richer our animation.

### On vendor prefixes
Vendor prefixes were originally created to allow browser makers to start supporting experimental CSS declarations. The vendor prefix kind of says “this is the Mozzilla interpretation of an ongoing proposal.”
It is a good policy to use vendor prefixes in your animations, as it allows the different browsers to render things in their way. So looking at our code, it would look something like this:

```css
@-webkit-keyframes example{
    0% {background-color: red;}
    100% {background-color: yellow;}
}
@-moz-keyframes example {
    0% {background-color: red;}
    100% {background-color: yellow;}
}
@-o-keyframes example {
    0% {background-color: red;}
    100% {background-color: yellow;}
}
@keyframes example {
    0% {background-color: red;}
    100% {background-color: yellow;}
}
```
And the corresponding CSS:

```css
div {
    width: 100px;
    height: 100px;
    background-color: red;
    animation-name: example;
    -webkit-animation-name: example;
    animation-duration: 4s;
    -webkit- animation-duration: 4s;
    }
```
And the same would be used for the -moz and -o prefixes.

And this is all we have to say about animations, from here is just a matter of creating more robust and complex animations, using the tools we presented here. ou canalso find some more examples of animations using CSS in this code repository (we be online soon) so be sure to check them.

Hope you enjoyed this little crash course.

Sincerely,
Cláudio Ribeiro

(Ongoing)

