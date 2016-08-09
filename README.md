# react-animatable-component

A react component that provides a standard API for transitioning elements in and out.


# Example Usage

```jsx
import AnimatableComponent from 'react-animatable-component';

export default class MyComponent extends AnimatableComponent {
    transitionIn(){
        return super.transitionIn().then(() => {
            // Do something that takes 500ms.
            return this.wait(500);
        }).then(() => {
            // Do something that else that takes 200ms.
            return this.wait(200);
        }).catch(() => {
            // Handle the animation being canceled.
        });
    }

    transitionOut(){
        // Do the opposite of what we did during the transition in.
        return super.transitionIn().then(() => {
            // Do something that takes 200ms.
            return this.wait(200);
        }).then(() => {
            // Do something that else that takes 500ms.
            return this.wait(500);
        }).catch(() => {
            // Handle the animation being canceled.
        });
    }
}
```
