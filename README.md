# jqueryDiscussion

jQuery Upgrade –Technical Document

2nd slide
(display table)
jQuery 1.10.2  ----------->  jQuery 2.2.1 + jQuery 1.4.1 migration plugin  ------------->  jQuery 3.3.1 + jQuery 3.3.0 migration plugin





3rd slide
jQuery
Remove jQuery.min.js from default.site which has version old jquery version
Deploy new file called as jquery-min.3.3.1.js into iwov-resources/scripts/web
Update default.site to use that script
Step 1
Put the version 2.2.1 along with jQuery migration plugin 1.4.1 into jquery-min.3.3.1.js file; Migration plugin will report deprecated messages
After loading the pages, check console window for any issues reported by the migration plugin
Fix the issues reported by migration plugin by using alternative functions from the new jQuery version
Step 2
Put the version 3.3.1 along with jQuery migration plugin 3.3.0 into jquery-min.3.3.1.js file
Repeat the process to check and fix issues
jQuery UI
jQuery UI is not used for all pages, i.e. not added in default.site
In pages where jQuery UI is added, update existing file to have the latest version 1.12
Test if the pages are working fine after the upgrade and fix any deprecated methods with the alternatives given for the new version

4th slide

jQuery
Deploy new file called as jquery-min.3.3.1.js into iwov-resources/scripts/js
Update all datacapture.cfg to use new jquery-min.3.3.1.js. During our analysis period we did not find any issues directly upgrading to 3.3.1
During SIT if we find any issues we will fix them
For TeamSite custom menu, where jQuery is used, replace the content with latest version

jQuery UI
Not used

5th slide
jQuery 2.2.1  +    jQuery 1.4.1 migration plugin

Deprecated Methods 2.2.1    -     Modified Methods in 2.2.1

$(window).load(function() { })   -   $(window).on('load',function() { });
.attr   -                             .prop
Number($(this).attr('data-slide-to')); - Number($(this).prop('dataset')["slideTo"]);
.size()           -                      .length
if ($.browser.msie && parseInt($.browser.version, 10) === 7) {}    --- if(document.all && !document.querySelector) { // browser version                                                                         checking here for IE7 }
if ($.browser.mozilla  && $(".customize-your-dbs").length > 0) {}   --- if ((typeof InstallTrigger !== 'undefined') && $(".customize-                                                                             your-dbs").length > 0) {}


6th slide
jQuery 3.3.1  +    jQuery 3.0.0 migration plugin
Deprecated Methods 3.3.1    --  Modified Methods in 3.3.1
.bind()  --- .on()
Y.find(":input,a").unbind("focus.jsp")   --- Y.find(":input,a").off("focus.jsp")
button.live('click', function() {});    ---- button.live('click', function() {});
this.$el.delegate(selector, eventName, method);  --- this.$el.on(eventName, selector, method);
selector.removeAttr( 'checked' );    ---- selector.prop( "checked", false);
$.parseJSON()    ---- JSON.parse()


7th slide
§Synchronous XMLHttpRequest

       In $.ajax() calls only XMLHttpRequest that's deprecated. The default is async: true. So need to change async: false. As of now we not changing it. It is not impacting.


 


  
 








 

 
  
  

  
 

