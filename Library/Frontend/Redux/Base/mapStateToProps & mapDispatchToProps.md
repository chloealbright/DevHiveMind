```javascript

// mapStateToProps & mapDispatchToProps has second param called ownProps which is rarely used but is used with conditional rendering

  

function ItemContainer (props) {

return (

<>

<h2>Item - {props.item}</h2>

<div>

<button onClick={props.buyItem}>Buy Items</button>

</div>

</>

)

}

  

const mapStateToProps = (state, ownProps) => {

const itemState = ownProps.cake

? state.cake.numOfCakes

: state.iceCream.numOfIceCreams

return {

item: itemState

}

}

  

// there will be situation where you dont want to subscribe to state and only pass dispatch to connect

const mapDispatchToProps = (dispatch, ownProps) => {

const dispatchFunction = ownProps.cake

? () => dispatch(buyCake())

: () => dispatch(buyIceCream())

return {

buyItem: dispatchFunction

}

}

  

export default connect(

mapStateToProps,

mapDispatchToProps

)(ItemContainer)

  

APP

<ItemContainer cake />

<ItemContainer /> // since no cake ice cream
```