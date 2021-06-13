Check it out here: https://navbar-salaarshafi.netlify.app/

This is a project showcasing my capabilities for responsive design and so there is no real content on the site except links and a button which is visible when the screen width is shorter and when clicked this button reveals the links in a list on the smaller screen so as not to cause clutter. When the screen size is less than a certain width the navbar is hidden and the above mentioned toggle button is displayed which you can use to hide or display the links.

A data.js file has been created from which the links data objects are imported as an array and also social media links data objects are imported too. This links data array is mapped and each data object is sent to an imported function called Navbar which returns a jsx component containing the links. Alternatively  the social media data array is also mapped but no imported function is used and it also returns a jsx component containing the social media icon links.

When the width of the screen is less than 800px by means of a media querie the class for showing social icons 'social-icons' changes it's display property's value to none hence not displaying any element having this class. The navbar links are also hidden when the screen width is less than 800px.

But a showlinks state is present in the main file which when the toggle button is displayed when the screen width is less than 800px is toggled between true or false. This state is used by a ternary operator present in the className attribute of the links container to return a 'show-links' class when the showlinks state is true which makes the links visible.

Two useRef properties have been set. One is the linksContainerRef and the other is the linksRef. A useEffect is used which checks every time the showLinks state changes using .current.getBoundingClientRect() the height of the linksRef and set's the linksContainerRef's height using the style attribute to the obtained measurement. This ensures no matter how many links need to be shown they will not be hidden because of over flowing and the linksRefContainer will adjust it's own height to accomodate all the links.
