Ultimate Module Creator 1.9.0-alpha2
======

New Ultimate Module Creator for Magento 1.7 +
-------------

This is the new version of <a href="https://github.com/tzyganu/moduleCreator">Ultimate Module Creator</a>. It is still under development so **DON'T USE IN PRODUCTION.**.  


This should be the version 2.0 of the Magento extension but I'm keeping this version for the Module Creator for Magento 2.0.  

Backwards compatibility has been broken.

If someone wants to help with the testing please submit any bugs, improvements or feature requests <a href="https://github.com/tzyganu/UMC1.9/issues">here</a>

Also any good code is welcomed.

**Note**
For the rest of the document UMC = Ultimate Module Creator

**Release Notes 1.9.0-alpha2 - 2014-04-03**

|Type|Label|Comment|
|----|-----|-------|
|Feature|Attribute notes for EAV entities are now manageable from the backend.|Attribute notes for EAV entities can be changed from the backend, when editing the attribute.|
|Bug fix|Attribute notes do not appear in the EAV entity form|<a href="https://github.com/tzyganu/UMC1.9/issues/10" target="_blank">#10</a>|
|Bug fix|Wrong EAV mass action flag change|<a href="https://github.com/tzyganu/UMC1.9/pull/8" target="_blank">#8</a>|
|Bug fix|The configuration panel for tree entities was incomplete|The display mode of tree entities was not manageable from the system configuration section.|
|Feature|Set the system configuration tab name and position.|You can set the configuration tab name and position when creating a module.|

**Release Notes 1.9.0-alpha1 - 2014-03-27**

|Type|Label|Comment|
|----|-----|-------|
|Bug fix|Fixed the sibling relation tab on admin.|For non tree entities related as siblings there was an error in the admin relation tab.|
|Bug fix|Fixed generation of uninstall script|The uninstall script tried to remove the module_eav_attribute table once for each EAV entity.|
|Bug fix|Image field/attribute display on frontend|The image attributes/fields were displayed wrong on frontend for EAV entities.|
|Bug fix|A file for generating content had a wrong name|<a href="https://github.com/tzyganu/UMC1.9/pull/6" target="_blank">#6</a>|


**Release Notes 1.9.0-dev8 - 2014-03-26** - Getting close to a stable version

|Type|Label|Comment|
|----|-----|-------|
|Improvement|Change module class aliases |Changed the class aliases from `module` to `namespace_module`. For example a model will be instantiated using `Mage::getModel('namespace_module/some_model')` to avoid extension conflicts. - the only things that does not use the namespace prefix are the SOAP API functions. It would look ugly with the namespace.|
|Feature|Added configurable frontend routes|The route of the module can be configured. (<a href="https://github.com/tzyganu/UMC1.9/issues/4">#4</a>)|
|Bug Fix|Fixed comment row URL|A click on any row on the comments grid ended up in a "Comment not found" error.|
|Bug Fix|Fixed entities in category page|Links to entities related to categories had a wrong format in the category view page.|

**Release Notes 1.9.0-dev7 - 2014-03-21**

|Type|Label|Comment|
|----|-----|-------|
|Feature|Added WS-I support for API for EAV entities|Added WS-I support for API for EAV entities and their attributes.|
|Bug Fix|Values for manually added attributes for EAV attributes are not saved|The values for manually added attributes for EAV entities were not saved due to the attributes not belonging to a group.|
|Bug Fix|Added `initLayoutMessages` for frontend controllers|Different types of session messages were not displayed in the entity actions (view/list) (<a href="https://github.com/tzyganu/UMC1.9/issues/2">(#2)</a>)|
|Bug Fix|Relations not saved when 3 or more entities exist|The entities relations were not displayed correctly when the module contained 3 or more entities. (<a href="https://github.com/tzyganu/UMC1.9/issues/5">(#5)</a>)|

**Release Notes 1.9.0-dev6 - 2014-02-14**

|Type|Label|Comment|
|----|-----|-------|
|Feature|Added support for SOAP API |The generated extensions can contain files used for the SOAP API.|
|Improvement|Added unique indexes to relation tables|The relation tables between entities and products or categories or other entities now have a unique index on the entity id and the related entity id.|
|Improvement|Changed the way sibling entities relations are saved|The sibling relations are not recreated completely anymore. They are merged.|
|Bug Fix |Fixed admin search|Selecting to include entities in admin search had no effect.|
|Useless|Added UI Effects|The UMC UI has pulsating and sliding effects on different operations.|

**Known issues 1.9.0-dev6**

The WS-I compliance does not work. (the file is not generated even. In the current state it will break the global WSDL).
The SOAP API for the generated modules is not fully tested.

**Release Notes 1.9.0-dev5 - 2014-02-06**

|Type|Label|Comment|
|----|-----|-------|
|Improvement|Comments grid include entity name|The admin grids for each entity comments include the entity name.|
|Feature|Added my comments for customers|There is a new section in the customer account menu that links to "my comments" for each entity.|
|Bug Fix|Fix url rewrite save|Flat entities with url rewrites and no stores could not be saved.|

**Release Notes 1.9.0-dev4 - 2014-02-04**

|Type|Label|Comment|
|----|-----|-------|
|Feature|Allowed more attribtues in mass action|Country and Dropdown attributes can be set by mass action from grid.|
|Bug fix|Fixed tree widget chooser|Tree widget chooser was giving fatal error.|
|Bug fix|Fixed relations between tree behaving entities|A "sibling" relation between and EAV Tree entity and a Flat Tree entity did not behave as expected. but this is no problem. No one will use this kind of relation.|
|Bug fix|Fixed RSS display|Now all attribute types displayed properly in the rss feed.|
|Bug fix|Fixed tree entities display|Tree entities rendered wrong when the view page was disabled.|
|Refactored|Widgets|Refactored widget view contents|

**Release Notes 1.9.0-dev3 - 2014-01-24**

|Type|Label|Comment|
|----|-----|-------|
|Feature|Drag & drop attributes|When creating an entity you can drag and drop attributes to sort them in the list|
|Feature|Select menu for entity link|Added ability to select the frontend menu where the link to your entity page should be placed|
|???|Temporarily disable API|The API does not yet work for EAV entities and comments. It is temporarily disabled until I get it working.|
|Bug fix|Empty page for non existing entities|The entity view page displayed as blank if looking at an entity that does not exist. Now redirects to 404 page.|
|Bug fix|Fixed display on category page|Entities related to categories were displayed on the category page at the top. Now they are after the product list.|
|Bug fix|Fixed entity relations |Entities can be related independent of their type|
|Bug fix|Fixed or generation for entities without url rewrites|Entities without url rewrites generated an empty url.|
|Bug fix|Fixed multiselect attributes in combination with url rewrite|For flat entities that have multiselect attributes and url rewrite the _beforeSave method was generated twice.|

**Release Notes 1.9.0-dev2**

|Type|Label|Comment|
|----|-----|-------|
|Refactor|Refactored some attribute codes|Variables that depend on attribute names now look like this: $someName instead of $some_name|
|Bug fix|Frontend layout file generation|Frontend layout file was always generated. Now is generated only if there is at least one entity that has frontend.|
|Bug fix|Fixed dropdown attributes for flat entities|Dropdown attribute for flat entities were not configured correctly in the admin grid and admin add/edid form.|
|Bug fix|Entities not displaying in product page.|Entities were not displaying in product page unless they had a separate view page.|
|Bug fix|Fixed field/attribute codes validation.|Field/Attribute codes use the same validation as product attributes|
|Bug fix|Replaced 'addFilter' with 'addFieldToFilter'|<a href="https://github.com/tzyganu/UMC1.9/issues/1">https://github.com/tzyganu/UMC1.9/issues/1</a>|
|Bug fix|Inconsistent registry naming |<a href="https://github.com/tzyganu/UMC1.9/issues/3">https://github.com/tzyganu/UMC1.9/issues/3</a>|


**Release Notes 1.9.0-dev1**

|Type|Label|Comment|
|----|-----|-------|
|Feature|Added EAV entities|Now you can create EAV entities that you can manage just like products and categories.|
|Feature|Added many to many link to categories|Now you can link you entities "many to many" with the catalog categories|
|Feature|Added comment feature|You can choose to allow customers to write comments on your entities.|
|Feature|Made extension "extensible"|Yeah...like someone is going to extend it|
|Feature|Many to many relations between tree entities|Now the tree entities can be related in "Many to many"|
|Feature|Module menu can be placed anywhere|Until now the menu could be placed in admin only on top level. Now it can be placed anywhere in the menu tree.|
|Feature|Added new attribute types|dropdown, multiselect. Can have different sources - still experimental.|
|Feature|Custom entities can be added as product, category and customer attributes.| |
|Feature|You can set the version of your generated module.|No more hard coded 0.0.1 version.|
|Refactor|Source file refactoring|Because some IDEs show errors when parsing incomplete PHP files I've removed the extension of the source files (etc/source)|
|Refactor|Refactored JS|The UI of the module creator now uses prototype classes instead of simple JS functions.|
|Refactor|UI refactor|'Pimped up' the UI of the module creator||
|Refactor|Removed frontend package and theme fields|base/default is used for all modules.|
|Refactor|Changed indentation from TAB to 4x space||
|Improvement|Improved speed of the module creator|No more AJAX calls to add an entity/attribute. The module save is done in the same step as validation.|
|Improvement|Module creator generate sql uninstall script|Along with the list of generated files now an sql uninstall script is generated for the created module.|
|Bug fix|Fixed bug that appears when there is an uppercase letter in the module name.|In previous version 'ModuleName' was not working on UNIX servers. Only 'Modulename'. This is fixed in this version.|  


