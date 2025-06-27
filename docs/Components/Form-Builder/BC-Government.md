[Home](index) > [Components](Components) > [Form Builder](Form-Builder) > **BC Government**

---

<!-- * [File Upload](#file-upload)
* [Business Name Search](#business-name-search)
* [BC Address](#bc-address) -->

![image](images/bc-gov.png)

## File Upload

<!-- **[Back to top](#top)** -->

With the CHEFS form builder, you have access to the 'File Upload' component, which enables you to attach files or documents to the form while submitting it. The maximum file size that can be uploaded using this component is 25MB, and all the files submitted through the form are securely stored in a designated Object storage space.

![File Upload Component](images/file-upload-1.png)

> **Note**: The max size per file for upload is 25MB.

### Configuration options

![File Upload Configuration](images/file-upload-2.png)

- Multiple files
- Add a label describing the Type of file you want people to upload (eg: 'resume' or 'cover letter')
- File Pattern - Specify allowed file extensions from the supported list below (e.g., .pdf, .docx, .jpg)

> **Note**: File Uploads are now available for all form types, including public forms, IDIR, and BCeID access forms. All uploaded files undergo security validation and virus scanning regardless of form access type.

### Allowed file types

CHEFS automatically restricts uploads to safe file types for security. The following file types are supported:

**Documents**

- PDF (.pdf)
- Microsoft Word (.doc, .docx)
- Text files (.txt)
- Rich Text Format (.rtf)
- OpenDocument Text (.odt)

**Images**

- JPEG (.jpg, .jpeg)
- PNG (.png)
- GIF (.gif)
- Bitmap (.bmp)
- SVG (.svg)

**Spreadsheets**

- Microsoft Excel (.xlsx, .xls)
- CSV (.csv)
- OpenDocument Spreadsheet (.ods)

**Presentations**

- Microsoft PowerPoint (.pptx, .ppt)
- OpenDocument Presentation (.odp)

**Media Files**

- Audio (.mp3, .wav)
- Video (.mp4, .avi, .mov, .wmv)

**Data Files**

- JSON (.json)
- XML (.xml)

### Blocked file types

For security reasons, the following file types are automatically blocked:

- **Executable files** - .exe, .bat, .scr, .com, .cmd, .msi, .app, .deb, .dmg, .run, .bin
- **Script files** - .js, .py, .rb, .sh, .ps1, .vbs
- **Web files** - .html, .php, .jsp, .asp
- **Archive formats that may contain executables** - .jar

### File Storage

Files uploaded via a CHEFS form are saved to a designated space in **Object storage**. The Object Storage Service is for Ministry and Greater Public Sector clients to store data as objects using standard protocols including S3, NFS, and HTTP. It provides a scalable, secure, fully managed object storage platform with high availability and enterprise features.

## Business Name Search

<!-- **[Back to top](#top)** -->

The "Business Name Search" auto-complete feature is a useful component that allows you to quickly find organizations by their name, business number, or BC Registries ID. The auto-complete feature helps save time and effort by eliminating the need to type out the full name or number of the organization you are searching for. Instead, you can select the suggested match from the drop-down list and find the organization you are looking for in seconds.

![Business name search](images/bc-business.png)

## BC Address

<!-- **[Back to top](#top)** -->

The BC Address auto-complete component is a preconfigured feature designed to help you quickly find BC addresses. As you enter your query, the tool generates a drop-down list of suggested matches, allowing you to easily select an option and save time and effort that would have been spent typing out the complete address.

This component stores a comprehensive set of address details, including geographic coordinates, full address, locality, province, and additional metadata used for geolocation accuracy. If your use case requires a lighter version that stores only essential data, consider using the [Simple BC Address](#simple-bc-address) component instead.

This is a preconfigured component. Please note that users can only change the 'Params' details as indicated in the following image. Please visit this link for more information: [Geocoder Developer Toolkit](https://bcgov.github.io/ols-devkit/examples/address_autocomplete.html)

![image](images/bc-address.png)

![image](images/bc-address-preview.png)

A similar component to the BC Address is the - [Advanced Fields – Address Component](Advanced-Fields#address) component, which helps you set up external providers like Google Maps, Azure Maps, OpenStreetMap Nominatim, or even a custom address API. This could be used for global address search.

## Simple BC Address

Simple BC Address is a simplified version of the [BC Address](#bc-address) component. It functions identically on the front end, allowing users to search and select addresses using autocomplete. The key difference lies in the data stored with the submission, Simple BC Address captures only essential information, whereas the BC Address component stores a more detailed dataset. You can see this difference when submission data is exported — the Simple BC Address exports fewer fields compared to the BC Address component, which includes more comprehensive location details.

This is a preconfigured component. Please note that users can only change the 'Params' details as indicated in the following image. Please visit this link for more information: [Geocoder Developer Toolkit](https://bcgov.github.io/ols-devkit/examples/address_autocomplete.html)

![image](images/simple-bc-address-params.png)

![image](images/simple-bc-address.jpg)

## Map Component

<!-- **[Back to top](#top)** -->

The "Map" component allows for a form designer to show a feature on the map for the submitter's reference, or allows for a user to submit one or many features to provide geospatial data for submission.
Current features supported include:

- Markers: Single Latitude and Longitude points on the map
- Circles: Single Latitude and Longitude points with an associated radius
- Polygons: A set of Markers which form a closed shape
- Line: A set of markers which do not form a closed shape

![image](images/map-component-1.png)

Additionally, base layers can be used to provide context to the map. These are background layers (e.g., OpenStreetMap, Light, Dark, Topographic) that can be customized or selected for display.

![image](images/map-component-custom-layer-mapview.png)

### Configuration Options

Under the "Data" Tab in the Map Component Settings, there are two subheadings: Default Values, and Submitter Options.

![image](images/map-component-edit.png)

#### Default Values

- Default Value: Choose what should be displayed on the map once the user loads the form. You can also specify the default base layer via selectedBaseLayer.
- Zoom Level: Choose how zoomed the map should be initially.
- Default Center: You can place a point on the displayed map to select where the map should be centered by default for the submitter.
- Default Base Layer: The base map shown when the map is first loaded (e.g., OpenStreetMap, Light, Dark, Topographic).

![image](images/map-component-edit2.png)

#### Submitter Options

- Allow submitters to add input on the map: This allows for users to add features to the map.
- Marker Type: Currently the map component supports Markers, Circles, Polygons, and Lines.
- Markers Per Submission: Select how many entries you would like the user to submit.
- Allow Submitters to Switch Base Layers: When enabled, users can toggle between predefined and custom base layers during form interaction.
- Available Base Layers for Submitters: Choose which base layers are available to users (OpenStreetMap, Light, Dark, Topographic).
  ![image](images/map-component-base-layer-options.png)
- Custom Base Layers: Designers can add their own tile layers with label, tile URL (must include {z}, {x}, {y}), and attribution. These can be toggled on/off and included in the map display.
- Enable Submitter "My Location" button: This button centers the map on the location provided by the user's browser.
- Enable BC Address Autocomplete: This enables a textbox which allows the user to type an address and have similar addresses appear in a dropdown. The user can then select an option and have the map center on the selected location. This dropdown uses the same service as the aforementioned BC Address form component.

<!-- **[Back to top](#top)** -->

---

- [Basic Layout](Basic-Layout)
- [Basic Fields](Basic-Fields)
- [Advanced Layout](Advanced-Layout)
- [Advanced Fields](Advanced-Fields)
- [Advanced Data](Advanced-Data)
- **BC Government**

---

[Terms of Use](Terms-of-Use) | [Privacy](Privacy) | [Security](Security) | [Service Agreement](Service-Agreement) | [Accessibility](Accessibility)
