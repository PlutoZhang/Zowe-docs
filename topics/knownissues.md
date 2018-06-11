# Known issues

When you initially open the MVD, a security message alerts you that you are attempting to open a site that has an invalid HTTPS certificate. Other apps within the MVD may also encounter this message. To prevent this message, add the URLs that you see to your list of trusted sites.

NOTE: If you clear the browser cache, you must add the URL to your trusted sites again.

zLUX APIs exist but are under development. Features might be reorganized if it simplifies and clarifies the API, and features might be added if applications can benefit from them.

While zLUX Authorization tuning allows for settings such as GET from Instance to work without login, **User** and **Group** Scope queries will be rejected if not logged in because they must obtain resources from a specific user. Because of this, **User** and **Group** Scopes will not be functional until the Security Framework is available. For more information, see [Resource Scopes](mvd-resourcescope.md).