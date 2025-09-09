#### readme makes no sense?
thats bcs i just stole it from a different repo, it doesnt make any sense out of context, idgaf tho

# LoveAffix
LoveAffix allows you to inject code between official love calls, for example, DepthDrawing uses this to cause draw calls to create an error when not drawing with a DepthDrawing.startDrawingAtDepth()
you are also able to alter inputs to functions for example: if you want to have every love.graphics.translate() call translate the world by an additional 30 pixels than you could use ```LoveAffix.injectCodiIntoLove(function(x, y) return x + 30, y end, "graphics", "translate");```
If you inject code into a love function and return any number of values then those values will be used as the arguments for the next (injected or official)
Injecting code effectively places it into a queue: injecting will place the code at the begining of the queue and whenever the function is called it will call all items in order.
You can also use ```LoveAffix.appendCodeIntoLove(apendedCode, key, [key2]);``` to place code at the end of the queue.

### IMPORTANT:
you are unable to inject or append code unless that function is prepped for it in love. you can do this by calling ```LoveAffix.makeCodeInjectable(key, [key2]);``` not all love items are valid for injection so be careful, but most things that you wold be using is.
there is no worry for calling ```LoveAffix.makeCodeInjectable(key, [key2]);``` on a function that is already prepped.
