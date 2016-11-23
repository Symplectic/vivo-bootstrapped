#The Symplectic Bootstrapped VIVO Theme
This repository contains the necessary template files for customizing the stock [VIVO](http://vivoweb.org/) interface to make it responsive and modern. You can read more about the release on the [Symplectic website](http://symplectic.co.uk/press/reimagining-research-profile-design-bootstrapped-vivo/). The theme was first presented at the VIVO Conference 2016, you can find the slides on [figshare](https://figshare.com/articles/Pimp_My_VIVO_Slides/3798105).

If you need a detailed explanation of setting up the VIVO environment, consult the
[VIVO installation instructions](https://wiki.duraspace.org/display/VIVODOC19x/Installing+VIVO).

##Prerequisites
You must have a working VIVO installation. Though this theme has been tested in the standard VIVO 1.8.1 build, we recommend the [three-tier](https://wiki.duraspace.org/display/VTDA/Building+VIVO+in+3+tiers) installation so that future updates to VIVO will not adversely effect the look and feel of the theme.

This theme uses [bootstrap](http://getbootstrap.com), the greatest framework invented for making a web project responsive. If you want to change the layout of the template files included in this theme, we recommend that you [read a bit more](https://getbootstrap.com/components/) about how the framework works.

The theme comes included with both CSS and [LESS](http://lesscss.org/features/) files for styling. However no LESS processor has been included in this repo, so if you would like to use LESS to change the styles, you will need to have a LESS to CSS compiler available either on your client or on the server. You can read more about getting started with LESS on their [website](http://lesscss.org/usage/#using-less-environments). The main advantage of using LESS is that you can change all the colors for the theme in one file included within the LESS folder.

If LESS is not for you, do not worry, the included CSS files are well commented to aid in your editing.

##Usage

###Deploying

Deploying the theme is really simple:

1. Copy the symplectic-bootstrapped-vivo folder into the "themes" directory in your VIVO root.
2. Build and deploy VIVO with Ant

    `ant all`

3. Restart the Tomcat service. The command will vary depending on OS. For Ubuntu/Linux:
    
    ~~~
    systemctl restart tomcat

    # Check if it started up succesfully
    systemctl status tomcat

    # You should get a response that contains
    #Active: active (running) since...
    ~~~

4. Login to VIVO via a browser and head to the **_Site Admin_** page and choose **_Site Information_**
5. Use the theme dropdown to select **_symplectic-bootstrapped-vivo_**. If you don't see it there, repeat steps 2 & 3.

###Making changes
The theme folder is structured as follows:
    
    
    |symplectic-bootstrapped-vivo
    |---css
        |---LESS
        |--openSocial
    |---fonts
    |---i18n
    |---images
    |---js
    |---templates
    

You can remove the LESS folder if you do not want to use it without effecting the styling of the theme.

The CSS folder contains the bootstrap project files, alongside a number of other CSS files. The only ones you will need to touch if you plan to change the color scheme are:
    
    
    -homepage.css
    -individual.css
    -theme.css
    

The templates folder contains 39 template files. These are all of the VIVO template files that have been modified to use the bootstrap framework.
**_Please note: This theme was designed on the display layer of VIVO, with the assumption that the data is will be fed from another system. The theme is unlikely to behave well for logged in users._**

As mentioned above, most of the site colours can be changed in the **_vars.less_** file contained in the less folder, but you will need a LESS compiler handy.

###Using Readcube, Altmetric & figshare integrations
This theme also includes integrations with Symplectic's sister companies, [figshare](http://figshare.com), [Altmetric](http://altmetric.com) & [Readcube](http://readcube.com). These integrations allow visitors to view the Altmetric score on research records, and if the record is available on figshare or readcube, use their appropriate embedded viewers to explore them further.

These integrations are reliant on VIVO referencing the DOI of a record, which does not currently come included in a standard VIVO installation. If you would like these integrations to work as expected, you will need to replace the **_listViewConfig-authorInAuthorship.xml_** file in your [VIVO-root]/productMods/config directory, with the one included in this repo.

###Fix for Map of Science throwing jQuery version errors
The later versions of jQuery required for Bootstrap appear to be clashing with the blockui jQuery plugin required for Map Of Science. You can fix this by removing the existing blockUI JS files in your [VIVO-root]/js/jquery_plugins folder and replacing it with the blockUI file included in this repo.

##License & Attribution

This theme is released under the terms of the Mozilla Public License, v. 2.0 and is a copyright of [Symplectic Limited](http://symplectic.co.uk). If a copy of the MPL was not distributed with this file, You can obtain one at http://mozilla.org/MPL/2.0/. Boiled down to smaller chunks, it can be described with the following conditions:

###This licence allows you to:
* Freely download, modify and use the Symplectic Bootstrap theme, in whole or in part, for personal, company internal or commercial purposes.

* Use the theme in packages or distributions that you create.

###This licence forbids you to:
* Hold the authors and license owners liable for damages as the theme is provided without warranty.

* Hold the creators or copyright holders of the theme, VIVO or Bootstrap liable.

* Use any marks owned by Symplectic in any way that might state or imply that Symplectic endorses your distribution.

###This licence does not require you to:
* Submit changes that you make to the theme back to the Symplectic project (though such feedback is always encouraged).

###External Attribution
This project would not have been possible without the help of the [Bootstrap framework](http://getbootstrap.com/getting-started/#license-faqs). Their full licence is available on the Bootstrap project [repository](https://github.com/twbs/bootstrap/blob/master/LICENSE).

