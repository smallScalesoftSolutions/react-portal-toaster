This component is made in React.
It is a toaster component.

npm start will serve the example folder at localhost:9000

The actual component lib code is in src folder.

/** This piece of code needs to be added one time in you application(most preferably in your in your root component) **/

import PortalContainer from "react-portal-toaster";

const config = {
    autoClose: true,
    closeTime: 1000
}

<PortalContainer config={config}/>

/** --------------END--------------------------------**/


/** To push the toaster from your code **/

import {SuccessToaster, ErrorToaster, InfoToaster} from "react-portal-toaster";
import {push} from "react-portal-toaster";

const NotificationBox = (props) => {
    return <SuccessToaster {...props}>Hello from Side Panel!!!!!!!</SuccessToaster>
}

// Can be done from inside a callback function //

push(NotificationBox, {
    autoClose: false
});

//---------------------------------------------//

/** -------------------END---------------------**/

The advantage of using this component is its flexibility to let the developers create their own toaster component
as per their UX design. For eg:- Instead of using SuccessToaster, you can create your own component and push it to react-portal-toaster.

const NotificationBox = (props) => {
  return return <div>
      <span>
        The toaster message can be added here
      </span>
      <span onClick={props.handleClose}>
        <div height="13px" width="13px" />
      </span>
    </div>;
}

// The only thing that we need from props here is handleClose

push(NotificationBox, {
    autoClose: false
});


