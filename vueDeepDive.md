## Reactivity
- State is application logic, side-effects are DOM mutations
- Linking side-effects to state changes transforms imperative code to declarative (?)
- Goal of frameworks is to allow the user to write something that is more declarative
- Vue, under the hood, whenever state changes it updates
- How do we detect that state has changed?
	- React works by the setState function
	- Angular uses dirty checking
		- Vue was created to explore a different strategy other than dirty checking
		- Vue said we don't want to support IE8 (like angulr) and therefore we get ES5 Object.define property

- Our dependency_tracking does not cover cleanup (different branches) and other edge cases

## Rendering
- On render -> Compiled to render function, generate virtual dom, apply to actual dom
- On Updates -> Render function, Diffed against old dom, Dom is updated
- Actual Dom = document.createElement('div')
- Virtual Dom = vm.$createElement('div')
	- Significantly cheaper (plain Javascript Objects are cheap)
- Virtual Dom: Essentially a lightweight javascript data format to represent what the actual DOM should look like at a given point in time
	- Decouples rendering logic from the actual DOM
	- A nice abstraction that makes rendering to multiple different sources clear
	- Helps with server-side rendering
	- Vue is agnostic to the render function; only cares that the Virtual DOM is generated.

- h can directly render a component

## State Management
- "Keeping it inside components: hoisting to common parent"
- Vuex gives structure, it is really just a wrapper on the 'naive store' implementation that gives us a convention to follow
- No best way of doing things at the moment

## Reuse and Composition

#### Mixins
- Best suited for logic that does not inject too many things into the component (maybe side effects or traits)
