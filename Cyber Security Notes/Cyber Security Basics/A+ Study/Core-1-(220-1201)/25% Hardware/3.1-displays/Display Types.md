### LCD
- **Liquid Crystal Display**
	- Light shines through **liquid crystals**
- Uses liquid crystal material that changes properties when voltage is applied
- Contains **RGB Subpixels** **for** red, green, and blue **(RGB) colours**
- **Resolution** determined by number of pixels per square inch
- **Layers** involved:
	1. Light Source
	2. Polarising filter
	3. Electrodes
	4. Liquid Crystal
	5. Electrodes
	6. Colour Filter
	7. Polarising filter
	8. Display surface
- **Standard LCD**:
	- Requires a **CCFL (Cold Cathode Fluorescent Lamp) backlight**
	- Needs and **inverter** to **convert** **DC** power to **AC** for the **CCFL**
- **Light Emitting Diode (LED) LCD**:
	- Uses **LED** backlight **instead** **of** a **CCFL**
	- Operates on DC power <- More energy efficient
	- Often **Thinner and lighter devices**
- **Advantages**:
	- Lightweight
	- Relatively low power <- Good for devices that run on a battery
	- Relatively inexpensive
- **Disadvantages**:
	- Black levels are difficult to achieve <- Difficult to produce a true black colour
	- Requires a separate backlight
		- Can be fluorescent, LED (Light Emitting Diode)
		- Lights can be difficult to replace
		- No backlight will often lead to a very dim, difficult to see, display
#### LCD Technologies
- **TN (Twisted Nematic) LCD**
	- Original LCD technology <- **Oldest** and **most basic**
	- **Fast response times** <- Good for **high motion applications** such as gaming
	- **Poor viewing angles** <- Colour shifts the further off angle a user is
	- **Poor Colour accuracy**
	- Commonly used in budget laptops and entry-level (budget friendly) devices
- **IPS (In Plane Switching) LCD**
	- **Rotates liquid crystals horizontally** to **improve colour accuracy** and **viewing angles**
	- **178 degree viewing angles** horizontally and vertically
	- **Excellent colour representation** (useful for tasks such involving  graphics such as video editing)
	- Typically **more expensive** to produce **than TN** (thus tends to cost more to purchase)
	- Preferred for smartphones, tablets, and high-end laptops
- **VA (Vertical Alignment) LCD**
	- **Compromise between TN and IPS**
	- **Best contrast ratios** (Difference between brightest shade and darkest shade luminance)
	- **Good colour representation** <- Deeper blacks, brighter whites
	- Typically **slower response times than TN and IPS**
	- **Narrower viewing angles than IPS panels**
	- Good for applications requiring high contrast
- Some devices may only have one style available, as such the best option should be chosen based on the intended use
###  Backlight and Inverter
- **LCD** Displays need a **backlight**
	- Fluorescent lamp or LED lights
- Power needs to be provided for a backlight
	- **Modern, LED, backlights** use the built in **Direct Current (DC)** used to power the device (e.g. a laptop)
	- **Older, Fluorescent, backlights** need to use **Alternating Current (AC)** since a device such as a laptop uses **DC**, the current must be **inverted** using an **inverter** so it becomes AC
- **Inverter** <- Used to **convert** **Direct Current** (DC) **to Alternating Current** (AC) such that it can be **used by** the **fluorescent lamp backlights**
	- Commonly used for Laptops <- often located within the bezel of the display
- Backlight functionality can be verified by turning on the device and looking closely at the screen
	- Useful to use a flashlight as the light will reflect from the back of the screen
	- If text or graphics can be seen faintly on the screen, there is likely an issue with the backlight
- A **backlight** will **eventually** need to be **replaced**
	- For devices using a **fluorescent backlight**, sometimes the **LCD Inverter** may also need to be **replaced**


### OLED
- **Organic Light Emitting Diode**
	- Uses an **Organic Compound** that **emits light** **when** an **electric current** is **received**
- **OLED Advantages**:
	- **Doesn't use** a **backlight**
		- Organic Compound provides the light
	- **Thinner and Lighter** than LCD due to the lack of a backlight component
		- Flexible and mobile <- doesn't need glass
			- Flexible materials allow for foldable and rollable displays
	- **More power-efficient** than LCD
	- Able to achieve **very accurate colour representation** <- **Superior contrast ratios** with true black colours
- **OLED Disadvantages**:
	- Tends to **cost** a bit **more** than LCD
	- **Lower brightness** than LCD <- Poor visibility in direct sunlight
	- Susceptible to **burn-in** (Static images can leave a permanent mark)
- Often used in tablets, phones, smart watches, and other mobile devices

### Mini LED
- **Mini Light Emitting Diode**
	- Same backlight tech as a conventional LED-backlit LCD but **uses the much smaller LEDs**
		- **Thousands** of tiny LEDs for highly localised backlighting zones
- **Mini LED Advantages**:
	- **Each individual LED can be controlled**:
		- Enabled/disabled individually
		- Each LED's light intensity can be adjusted
		- The colour of each LED can be changed
	- Much better control over dark screen areas
	- **Better colour representation** e.g.  **deeper blacks**
	- **Improved contrast** and **brightness** compared to traditional **LED-backlit LCDs**
	- **Balance** between **affordability** and **high-quality visuals**
- Popular in premium laptops and tablets
- Conventional LED backlight vs Mini LED:
	![[Pasted image 20260830065418.png]]

### Touchscreen
- **Uses a digitiser in response to touch, which converts each touch into a series of co-ordinates**
- **Removes the need for certain hardware** such as **keyboards** by using the screen itself as the input
	- Some laptops, tablets, and other touchscreen devices still have the option for a physical keyboard to be used too
- Grants **many input options**, e.g. mouse vs digitiser, physical vs digital keyboard
	- Allows users to select one that best fits their preference or task
- Different **types of touchscreens**:
	- **Capacitive Touchscreens**
		- Sense **electrical changes** in an **electrostatic field** caused by touch in order to **detect input** instead of requiring physical pressure
		- Two **sub-types**:
			- **Surface Capacitive (SCAP)** <- Single Touch only
			- **Project Capacitive (P-Cap)** <- Multi-touch supporting upwards of 5-10 contact points at once
		- **Advantages of SCAP**:
			- **Cost-effective** and **simple**
		- **Disadvantages of SCAP**:
			- **Only** support **single-touch input**
	- **Multi-Touch Screens** <- Often using **Projected Capacitive (P-Cap)**
		- **Advantages** of **P-Cap**:
			- Supports **multiple contact points** at the same time
			- Enable **advanced gestures/interactions** such as **pinch-to-zoom** and **multi finger swipes**
		- **Disadvantages** of P-**Cap**:
			- **More expensive** 
		 - Widely used in smartphones and tablets
	- **Resistive Touchscreens**
		- Detects touch input through **physical pressure**
		- Two flexible conductive layers separated by a small gap
			- Upon touch, top layer bends to touch bottom layer, which creates an electrical connection
			- Upon electrical connection, a controller measures the change in voltage at the point of contact to calculate the precise coordinates of the input
		- **Advantages**:
			- Versatile, working with gloves, styluses, and any object <- input doesn't need to be conductive
			- Better for harsh environments where a screen may be exposed to dust, moisture, or extreme temperatures
			- Often less expensive to manufacture
		- **Disadvantages**:
			- Single touch limitation
			- Typically offer lower image clarity and brightness due to the additional layers
#### Digitiser
- Many digitisers also allow for the use of a **Stylus** for inputs as well as a user's finger
	- Useful for graphical input such as digital art
- Commonly used for tablets, some laptops, even some hybrid devices such as desktop computers

### Choosing A Display Type
- **Touch input:**
	- **Capacitive Touchscreen**:
		- **SCAP** for cost-effectiveness
		- **P-Cap** (Multi-touch screens) for enhanced functionality
	- **Resistive Touchscreen** for cost-effectiveness, durability and touch versatility
- **Display Quality and Efficiency:**
	- **Twisted Nematic (TN)** panels for **budget** applications
	- **In Plane Switching (IPS)** panels for high **colour accuracy** and **wide viewing angles**
	- **Organic Light Emitting Diode (OLED)** for superior **contrast** and **flexibility**
	- **Mini-Light Emitting Diode (Mini-LED)** for high **brightness** and **affordability**
##### Use case Examples
- Budget Smartphones:
	- Twisted Nematic (TN) LCD panels for cost saving
- High-end flagship devices:
	- Organic Light Emitting Diode (OLED) displays for image quality
- Professional-grade Laptops:
	- In Plane Switching (IPS) or Mini-LED for colour accuracy