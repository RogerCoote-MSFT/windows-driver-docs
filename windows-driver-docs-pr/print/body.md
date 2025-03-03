---
title: body element
description: The required body element provides text that is displayed in the event notification message. This text should provide the user specific details about the printer event.
keywords: ["body element Print Devices"]
topic_type:
- apiref
api_name:
- body
api_type:
- Schema
ms.date: 11/28/2017
---

# body element

The required **body** element provides text that is displayed in the event notification message. This text should provide the user specific details about the printer event.

The **body** element is defined in the *asyncui* namespace at this URI:

```xml
https://schemas.microsoft.com/2003/print/asyncui/v1/request
```

This resource may not be available in some languages and countries.

## Usage

```xml
<body
  stringID = "xs:string"
  resourceDll = "xs:string">
  child elements
</body>
```

## Attributes

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribute</th>
<th>Type</th>
<th>Required</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>resourceDll</strong></p></td>
<td><p>xs:string</p></td>
<td><p>No</p></td>
<td><p></p>
<p>An optional attribute that specifies a resource DLL that contains the body text to display in the event notification message. This DLL should be a dependent file of the printer driver and must be present in the driver resource folder (for example, %SYSTEMROOT%\system32\spool\drivers\w32x86\3).</p></td>
</tr>
<tr class="even">
<td><p><strong>stringID</strong></p></td>
<td><p>xs:string</p></td>
<td><p>Yes</p></td>
<td><p></p>
<p>A required attribute that specifies the text to display in the body of the event notification message. The attribute value specifies the location of the text string in the resource DLL.</p></td>
</tr>
</tbody>
</table>

## Child elements

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="parameter.md" data-raw-source="[&lt;strong&gt;parameter&lt;/strong&gt;](parameter.md)"><strong>parameter</strong></a></p></td>
<td><p></p>
<p>An optional element that specifies text strings that substitute for parameters in a body text specification.</p></td>
</tr>
</tbody>
</table>

## Parent elements

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="balloonui.md" data-raw-source="[&lt;strong&gt;balloonUI&lt;/strong&gt;](balloonui.md)"><strong>balloonUI</strong></a></p></td>
<td><p></p>
<p>An optional element that is used to display a message balloon on the client computer.</p></td>
</tr>
<tr class="even">
<td><p><a href="messageboxui.md" data-raw-source="[&lt;strong&gt;messageBoxUI&lt;/strong&gt;](messageboxui.md)"><strong>messageBoxUI</strong></a></p></td>
<td><p></p>
<p>An optional element that is used to display a message box on the client computer.</p></td>
</tr>
</tbody>
</table>

## Remarks

The body text loaded from the resource DLL can contain percentage (%) tags that will be replaced with text strings specified by the [**parameter**](parameter.md) child element.

Multiple **body** tags can be used sequentially, in which case the text generated by each will be concatenated in the event notification message. A space will be inserted between each pair of text strings. The same notification message can display both: status information, such as "Your printer is out of ink.", and instructions for the user, such as "Replace the ink cartridge and press the Resume button on the printer to continue."

The text contained in the **body** element should let the user know what action is available.

Use the following recommendations to keep the message text useful and concise:

- Use complete sentences with ending punctuation.
- Compose body text that can be less than 255 characters when localized into other languages. For example, a message in English should typically not use more than 200 characters in order to accommodate localization into other languages.
- Include essential information that allows the user to complete a requested action, such as specific object names, user names, file names, or URLs. Users should not have to open another window to find such information.
- Place double quotation marks around object names (for example, "Paper Bin 1"). However, do not use quotation marks when the object name uses capitalized words, such as a user name, it is offset with a colon (for example, Printer name: My printer), or it can be easily determined from the context.
- If you have to truncate object names to a fixed maximum size to accommodate localization, use an ellipsis (...) to indicate truncation.
- If a notification message provides a button for user action, make sure there are two line breaks between message information and the button. Label the button with simple action-oriented phrases, such as, "Click to Restart Printing," or "Click to see more information."
- Only use notification messages for non-critical information that the user can freely ignore. The body text should not say that the user must perform an action.
- If the user should perform an action, clearly describe the importance and consequences of performing the action.
- Describe problems in plain language with specific information about how the user can fix the problem.
- Describe the event in a way that is relevant to the user. A notification message is relevant if there is a reasonable chance that a user will perform a task or change behavior as a result of the notification.
- Describe an event in terms of user goals, rather than in terms of technological issues.

## Examples

The following code example shows how to use the **body** element.

```xml
<?xml version="1.0" ?>
   <asyncPrintUIRequest
    xmlns="https://schemas.microsoft.com/2003/print/asyncui/v1/request">
    <v1>
      <requestOpen>
        <balloonUI iconID="1" resourceDll="IHV.dll">
          <title stringID="1234" resourceDll="IHV.dll" />
          <body stringID="100" resourceDll="IHV.dll">
            <parameter stringID="5" />
            <parameter stringID="1002" resourceDll="IHV.dll" />
          </body>
        </balloonUI>
      </requestOpen>
    </v1>
  </asyncPrintUIRequest>
```

## See also

[balloonUI](balloonui.md)

[messageBoxUI](messageboxui.md)

[parameter](parameter.md)
