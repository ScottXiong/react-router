```
import React from 'react';
import ReactDOM from 'react-dom';
import {BrowserRouter as Router, Link, Route} from 'react-router-dom'

import 'font-awesome/css/font-awesome.min.css';
import './index.css';
import './index.scss';

//life circle

class A extends React.Component{
  constructor(props){
    super(props)
  }
  render(){
    return <h1>{this.props.children}</h1>
  }
}

function C(){
  return (
     <div>
       <h3>I am Component C</h3>
     </div>
    )
}

const D=()=>{
  return <div>
    <h3>hello world</h3>
  </div>
}

class App extends React.Component {
   render(){
    return(
      
       <Router>
         <div>
         <Link to={`/g/id`}>
           带参数的跳转
         </Link>
          <Link to={`/`}>
           不带参数的跳转
         </Link>
          <A>
            <Route exact={true} path='/' render={()=>(
              <div>
               <ul>
                 <li>apple</li>
                 <li>pera</li>
               </ul>
              </div>
              )} />
            <Route path='/g/:id' component={D}/>
          </A>      
         </div>
       </Router>          
       
      )
   }
}
ReactDOM.render(
       <App/>,
    document.getElementById('app')
);

```
