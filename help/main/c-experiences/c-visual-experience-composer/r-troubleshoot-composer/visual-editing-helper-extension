---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Discover why some websites might not open reliably in the [!UICONTROL Visual Experience Composer] (VEC). The [!UICONTROL Visual Editing Helper] browser extension lets you load websites reliably within the VEC.
title: How Do I Use the [!UICONTROL Visual Editing Helper] Extension?
feature: Visual Experience Composer (VEC)
---
# [!UICONTROL Visual Editing Helper] extension

The [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] browser extension for Google Chrome lets you load websites reliably within the [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) to rapidly author and QA web experiences. 

>[!IMPORTANT]
>
>This new extension replaces the previous [Target VEC Helper browser extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## Reasons why some websites might not open reliably in the VEC

* The website has strict security policies.
* The website is in an iframe.
* The customer's QA or stage site is not available to the outside world (the site is internal).

The [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] browser extension for Chrome solves site-loading issues for which customers now rely on the [!DNL Target] [!UICONTROL [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)] or third-party extensions, such as Requestly.

## Benefits of using the [!UICONTROL Visual Editing Helper] extension

* All iframe busting headers, such as `X-Frame-Options` and `Content-Security-Policy`, are implicitly removed from the website. There is no need to create complicated Requestly rules.
* If a webpage does not yet contain the [!DNL Target] at.js library, you can use the extension to inject the library so you can author experiences for the website. You can then create activities and QA them using preview links.

Note that using the [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec)], the extension does not inject at.js, but the SameSite Cookie functionality is still present. To inject at.js on the webpage, turn off the EEC.

* [Mobile viewports](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) are supported even without the [!UICONTROL Enhanced Experience Composer] (EEC).
* Customers new to [!DNL Target] can use the extension to experiment with [!DNL Target] even if their IT developers have not yet implemented [!DNL Target] on their websites.
* Partners servicing multiple customers' websites and [!DNL Target] accounts now have one simple mechanism to support VEC loading, instead of managing multiple rules in third-party tools.

## Obtain and install the [!UICONTROL Visual Editing Helper] browser extension

1. Navigate to the [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Click **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. Open the VEC in [!DNL Target].
1. To use the extension, click the [!UICONTROL Visual Editing Helper] browser extension icon ( ![Visual Editing Extension icon](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) in your Chrome browser's toolbar while in the VEC or QA Mode.

   The [!UICONTROL Visual Editing Helper] is automatically enabled when a website is opened in the [!UICONTROL Target] VEC to power authoring. The extension doesn't have any conditional settings. The extension handles all the settings automatically, including SameSite cookies settings.

   For more information on the `SameSite=None` attribute browser fix, see "How do the recently announced Google Chrome SameSite cookie enforcement policies impact the VEC and EEC?" in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notes

* For [!DNL Target], the extension loads the latest version of at.js that is available from the [!DNL Target] UI in [!UICONTROL Administration] > [!UICONTROL Implementation] and at.js downloads the authoring libraries.
* When using the extension to inject at.js while in [QA Mode](/help/main/c-activities/c-activity-qa/activity-qa.md), you must have another Chrome tab open. This Chrome tab must be authenticated to the same [!DNL Adobe Experience Cloud] organization in which you created the activity.
* The following messages help keep you informed:

  * If you attempt to load a website using the VEC that fails to load, a message displays suggesting that you install the [!UICONTROL Visual Editing Helper] browser extension.
  * If at.js or alloy.js is not yet implemented on the website, a message displays in the VEC suggesting that you install the extension.

## More help on this feature

* [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md)
* [Troubleshooting Issues Related to the Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md)
* [Troubleshooting Issues Related to the Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md)



