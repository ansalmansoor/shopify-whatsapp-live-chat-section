# Shopify WhatsApp Live Chat Section

A lightweight, advanced, and speed-optimized Shopify OS 2.0 section for adding a floating WhatsApp live chat button to your Shopify store.

This project uses a single Shopify Liquid section file. No external CSS file, JavaScript file, image file, or Shopify app is required.

---

## Features

* Single Shopify section file
* Floating WhatsApp live chat button
* Show on homepage only or globally on all pages
* Custom WhatsApp number
* Custom desktop button text
* Custom mobile button text
* Dynamic current page URL inside WhatsApp message
* Separate desktop and mobile position settings
* Separate desktop and mobile size settings
* Separate desktop and mobile padding settings
* Custom colors
* Custom border width
* Custom border radius
* Custom shadow
* Optional pulse animation
* Inline SVG WhatsApp icon
* No external image request
* No external JavaScript
* No external CSS
* Google PageSpeed friendly
* Shopify OS 2.0 compatible

---

## Project Structure

Your GitHub repository should look like this:

shopify-whatsapp-live-chat-section/
├── README.md
└── sections/
└── whatsapp-live-chat.liquid

Optional .gitignore:

shopify-whatsapp-live-chat-section/
├── README.md
├── .gitignore
└── sections/
└── whatsapp-live-chat.liquid

---

## Installation: Create Shopify Section File

Go to your Shopify admin:

Online Store → Themes → Edit code

Open the sections folder.

Click:

Add a new section

Name the section:

whatsapp-live-chat

Shopify will create this file:

sections/whatsapp-live-chat.liquid

Delete the default code and paste the section code from this project.

Click Save.

---

## Show Button on Homepage Only

Use this method if you only want the WhatsApp button on the homepage.

Go to:

Online Store → Themes → Customize

Open the homepage.

Click:

Add section

Select:

WhatsApp live chat

Configure the button settings.

Click Save.

---

## Show Button on Every Page

Use this method if you want the WhatsApp button to show on:

* Homepage
* Product pages
* Collection pages
* Cart page
* Blog pages
* Article pages
* Normal pages

Open this file:

layout/theme.liquid

Find this line near the bottom:

</body>

Paste this code just above it:

{% section 'whatsapp-live-chat' %}

Final example:

```
{% section 'whatsapp-live-chat' %}
```

  </body>
</html>

Click Save.

---

## Important Checkout Note

This section will not show on Shopify checkout pages unless your store is on Shopify Plus.

Normal Shopify themes cannot edit checkout layout globally.

---

## Basic Settings

After installing the section, go to:

Online Store → Themes → Customize

Find:

WhatsApp live chat

Available basic settings:

| Setting                    | Description                            |
| -------------------------- | -------------------------------------- |
| Enable button              | Turns the WhatsApp button on or off    |
| WhatsApp number            | Your WhatsApp number with country code |
| Desktop button text        | Text displayed on desktop              |
| Mobile button text         | Text displayed on mobile               |
| Prefilled WhatsApp message | Message added before current page URL  |
| Accessibility label        | Screen-reader label                    |
| Open in new tab            | Opens WhatsApp in a new browser tab    |

---

## WhatsApp Number Format

Use your WhatsApp number with country code.

Correct:

919846256563

Wrong:

+91 98462 56563
91-98462-56563
(91) 98462 56563

Do not add:

*

spaces
brackets
dashes

---

## WhatsApp Message Behavior

The section automatically adds the current page URL to the WhatsApp message.

Example:

Hello! I am interested in your product from this page: https://yourstore.com/products/example-product

This helps you know which product or page the customer is asking about.

---

## Desktop Position Settings

Available desktop positions:

* Bottom left
* Bottom right
* Top left
* Top right

Recommended desktop values:

Position: Bottom left
Side spacing: 20px
Top/bottom spacing: 20px

---

## Mobile Position Settings

Available mobile positions:

* Bottom left
* Bottom right
* Top left
* Top right

Recommended mobile values:

Position: Bottom left
Side spacing: 14px
Top/bottom spacing: 24px

---

## Desktop Style Settings

Available desktop style settings:

* Desktop text size
* Desktop icon size
* Desktop vertical padding
* Desktop horizontal padding
* Desktop icon/text gap
* Desktop border radius

Recommended desktop values:

Text size: 14px
Icon size: 24px
Vertical padding: 8px
Horizontal padding: 20px
Icon/text gap: 8px
Border radius: 30px

---

## Mobile Style Settings

Available mobile style settings:

* Mobile text size
* Mobile icon size
* Mobile vertical padding
* Mobile horizontal padding
* Mobile icon/text gap
* Mobile border radius
* Hide text on mobile

Recommended mobile values:

Text size: 12px
Icon size: 20px
Vertical padding: 6px
Horizontal padding: 14px
Icon/text gap: 6px
Border radius: 30px

For an icon-only mobile button, enable:

Hide text on mobile, icon only

---

## Color Settings

You can customize:

* Button background
* Button text
* Button border
* Icon background
* Icon color
* Hover background
* Hover text
* Hover border
* Keyboard focus color

Recommended WhatsApp style:

Button background: #FFFFFF
Button text: #111111
Button border: #25D366
Icon background: #25D366
Icon color: #FFFFFF
Hover background: #25D366
Hover text: #FFFFFF
Hover border: #25D366
Keyboard focus color: #25D366

---

## Border and Shadow Settings

Available settings:

* Border width
* Shadow color
* Shadow vertical offset
* Shadow blur

Recommended values:

Border width: 2px
Shadow color: #000000
Shadow vertical offset: 4px
Shadow blur: 12px

---

## Animation Settings

Available settings:

* Enable pulse animation
* Pulse size
* Hover lift

Recommended values:

Pulse animation: Disabled
Pulse size: 8px
Hover lift: 2px

For best Google PageSpeed performance, keep pulse animation disabled.

---

## Advanced Settings

Available settings:

* Font weight
* Z-index

Recommended values:

Font weight: Bold
Z-index: High

Use Very high if the button is hidden behind another app, sticky footer, chat widget, or announcement bar.

---

## Google PageSpeed Optimization

This section is optimized because:

* No external CSS file is loaded
* No external JavaScript file is loaded
* No image file is loaded
* WhatsApp icon is inline SVG
* Mobile and desktop text switching uses CSS
* No JavaScript resize listener is used
* The section only renders when enabled
* The code uses simple Liquid and CSS

---

## Common Issue: Button Shows Only on Homepage

This happens when the section is added only through the homepage customizer.

To show it everywhere, open:

layout/theme.liquid

Find:

</body>

Add this above it:

{% section 'whatsapp-live-chat' %}

---

## Common Issue: Button Not Showing

Check these settings:

Enable button = checked
Show on desktop = checked
Show on mobile = checked
WhatsApp number = added correctly

Also confirm this file exists:

sections/whatsapp-live-chat.liquid

If you want global display, confirm this code is inside:

layout/theme.liquid

Code:

{% section 'whatsapp-live-chat' %}

---

## Common Issue: Liquid Syntax Error with Remove Filter

Do not write Shopify Liquid filters like this:

assign phone_clean = s.phone_number
| remove: '+'
| remove: ' '

Use one line:

assign phone_clean = s.phone_number | remove: '+' | remove: ' ' | remove: '-' | remove: '(' | remove: ')'

This project already uses the fixed version.

---

## Common Issue: Invalid Schema Range Step

Shopify range settings must have at most 101 steps.

Invalid:

"min": 0,
"max": 120,
"step": 1

This creates 121 steps, so Shopify blocks saving.

Correct:

"min": 0,
"max": 120,
"step": 2

This project already includes the fixed version.

---

## Optional .gitignore

Create a file named:

.gitignore

Add this:

.DS_Store
node_modules/
.env

Do not put .gitignore content inside README.md.

---

## GitHub Upload Steps

### Upload Using GitHub Website

1. Create a new GitHub repository.
2. Name it:

shopify-whatsapp-live-chat-section

3. Upload this structure:

README.md
sections/whatsapp-live-chat.liquid

4. Optional: upload .gitignore.
5. Click Commit changes.

---

## Upload Using Git Command Line

Run these commands inside your project folder:

git init
git add .
git commit -m "Initial commit: Shopify WhatsApp live chat section"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/shopify-whatsapp-live-chat-section.git
git push -u origin main

Replace:

YOUR-USERNAME

with your GitHub username.

---

## Recommended Shopify File Location

The Liquid file should be here:

sections/whatsapp-live-chat.liquid

Not here:

whatsapp-live-chat.liquid

If the Liquid file is in the root folder, move it into the sections folder.

---

## Usage Summary

Homepage only:

Add section from Shopify theme customizer

All pages:

{% section 'whatsapp-live-chat' %}

Place it above:

</body>

inside:

layout/theme.liquid

---

## License

You can use, edit, and customize this section for your Shopify store projects.
