# Components, states, and interoperation among them

React allows the development of components in hierarchies. As an example, a main window frame can have a window inside. And inside a window you can have a bird:

```
<windowFrame>
  <windowSpace>
    <bird />
  </windowSpace>
</windowFrame>
```

Because life is life, all these elements have attributes, the window have frame, for example, have color. The window space have size, and the bird is hungry so the bird can eventually become bigger in size. These attributes can be considered states and it's easy to see them in isolation. The bird's state, the windowSpace state and the windowFrame state.

When looking at the states in isolation it's all very simple but the problem with that is that it does not work like real life. That because in reality the states of one element may impact or relate to the state of other element. As an example, if you feed the bird too much, it will grow in size and it may not fit the window space anymore.

In order to implement a solution that works more like real life, we need states to "talk" each other. In the more traditional paradigm of programming, the solution to the problem could be as easy as to put a conditional in the parent component, for example to have the windowSpace to check the bird's size state, and then if the bird' size is too big, the window can ask the bird to leave; or the other way around which is to have the bird check the size of the space and if is too tight then the bird leaves.

The decision on which component to have the conditional check is usually a developer's decision based in demands of the problem. It would also be common situation for both components to negotiate. Say the bird wants to know the size available but also the windowSpace have certain rules, such as to always allow space for a new bird.

## Why and how to conciliate component hierarchies with shared states  
