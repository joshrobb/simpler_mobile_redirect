About Simpler Mobile Redirect
----------------------------
Simpler Mobile Redirect is a hacked up version of Simple Mobile Redirect. 

It's "simpler" than SMR because it always redirects mobile devices to the mobile version of a site unless they specifically ask it not to (using ?nomobi=true). 

Non-mobile devices will never be redirected unless they specifically request to view the mobile site using ?nomobi=false

It will redirect you to the same node on the destination site so it's assumed the sites have the same structure/urls. If you don't want to do this - just use /?nomobi=true and it'll redirect to the root (or [siteroot]).

Here's the state machine: 

				| Site						View Desktop Site			View Mobile	
				|							?Nomobi=true				?Nomobi=false	
Mobile device?	| Mobile Site	DesktopSite	Desktop Site	Mobile Site	Desktop Site	Mobile Site
-----------------------------------------------------------------------------------------------
Yes				| Nothing		Redirect	Nothing			Redirect	Redirect		Nothing
No				| Nothing		Nothing		Nothing			Redirect	Redirect		Nothing


Current features:

* Separate redirects for iPad, IPhone, Andriod, Opera Mini, Blackbery
* Disable redirect with a cookie set at ?nomobi=true
* Remove the cookie at ?nomobi=false (triggers a redirect to the mobile site; rel="nofollow" recommended)
