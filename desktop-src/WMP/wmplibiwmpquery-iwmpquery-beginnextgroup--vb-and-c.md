---
title: IWMPQuery beginNextGroup method
description: The beginNextGroup method begins a new condition group.
ms.assetid: 15d20c9f-2ce7-4a86-9054-b7317ebe1a0a
keywords:
- beginNextGroup method Windows Media Player
- beginNextGroup method Windows Media Player , IWMPQuery interface
- IWMPQuery interface Windows Media Player , beginNextGroup method
topic_type:
- apiref
api_name:
- IWMPQuery.beginNextGroup
api_location:
- Interop.WMPLib.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IWMPQuery::beginNextGroup method

The **beginNextGroup** method begins a new condition group.

## Syntax


```CSharp
public void beginNextGroup();
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>Public Sub beginNextGroup()
Implements IWMPQuery.beginNextGroup</code></pre></td>
</tr>
</tbody>
</table>



## Parameters

This method has no parameters.

## Return value

This method does not return a value.

## Remarks

Beginning a new condition group implies that you have completed the current condition group. The new condition group is always concatenated to the previous condition group by using **OR** logic.

## Examples

The following example creates a complex query by combing two groups that each contain a condition. The results of the query are extracted as a string collection and displayed in a list box. The **AxWMPLib.AxWindowsMediaPlayer** object is represented by the variable named player.


```CSharp
// Get a new Query interface.
WMPLib.IWMPMediaCollection2 mc = (WMPLib.IWMPMediaCollection2)player.mediaCollection;
WMPLib.IWMPQuery q = mc.createQuery();

// Add a condition to the Query. 
q.addCondition("WM/Composer", "Equals", "Antonio Vivaldi");

// Begin another Query group.
q.beginNextGroup();

// Add a condition to the new group understanding that it will be combined with the
// first group using OR logic.
q.addCondition("Title", "Contains", "Capriol");

// Query the media collection and get a string collection containing the result.
// In this case, the string collection will contain the titles of all audio items that
// match the query.
WMPLib.IWMPStringCollection2 result = (WMPLib.IWMPStringCollection2)mc.getStringCollectionByQuery("Title", q, "audio", "", false);

// Display the results by adding them to a list box.
for (int i = 0; i < result.count; i++)
{
    complexQueryResults.Items.Add(result.Item(i));
}
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>&#39; Get a new Query interface.
Dim mc As WMPLib.IWMPMediaCollection2 = player.mediaCollection
Dim q As WMPLib.IWMPQuery = mc.createQuery()

&#39; Add a condition to the Query. 
q.addCondition(&quot;WM/Composer&quot;, &quot;Equals&quot;, &quot;Antonio Vivaldi&quot;)

&#39; Begin another Query group.
q.beginNextGroup()

&#39; Add a condition to the new group understanding that it will be combined with the
&#39; first group using OR logic.
q.addCondition(&quot;Title&quot;, &quot;Contains&quot;, &quot;Capriol&quot;)

&#39; Query the media collection and get a string collection containing the result.
&#39; In this case, the string collection will contain the titles of all audio items that
&#39; match the query.
Dim result As WMPLib.IWMPStringCollection2 = mc.getStringCollectionByQuery(&quot;Title&quot;, q, &quot;audio&quot;, &quot;&quot;, False)

&#39; Display the results by adding them to a list box.
For i As Integer = 0 To (result.count - 1)

    complexQueryResults.Items.Add(result.Item(i))

Next i</code></pre></td>
</tr>
</tbody>
</table>



## Requirements



|                      |                                                                                                                        |
|----------------------|------------------------------------------------------------------------------------------------------------------------|
| Version<br/>   | Windows Media Player 11.<br/>                                                                                    |
| Namespace<br/> | **WMPLib**<br/>                                                                                                  |
| Assembly<br/>  | <dl> <dt>Interop.WMPLib.dll (Interop.WMPLib.dll.dll)</dt> </dl> |



## See also

<dl> <dt>

[**IWMPMediaCollection2.createQuery (VB and C#)**](wmplibiwmpmediacollection2-iwmpmediacollection2-createquery--vb-and-c.md)
</dt> <dt>

[**IWMPMediaCollection2.getPlaylistByQuery (VB and C#)**](wmplibiwmpmediacollection2-iwmpmediacollection2-getplaylistbyquery--vb-and-c.md)
</dt> <dt>

[**IWMPMediaCollection2.getStringCollectionByQuery (VB and C#)**](wmplibiwmpmediacollection2-iwmpmediacollection2-getstringcollectionbyquery--vb-and-c.md)
</dt> <dt>

[**IWMPQuery Interface (VB and C#)**](iwmpquery--vb-and-c.md)
</dt> </dl>

 

 




