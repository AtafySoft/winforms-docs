---
title: Free Form Date Time Parsing
page_title: Free Form Date Time Parsing
description: Free Form Date Time Parsing
slug: editors-timepicker-enable-free-form-date-time-parsing
tags: free,form,date,time,parsing
published: True
position: 4
---

# Free Form Date Time Parsing



From Q2 2014 we introduced new MaskType of RadMaskedEditBox that is designed to work with DateTime objects and it is not format restricted as the old one.
        With the new MaskType RadMaskedEditBox tries to parse the input string to valid DateTime object by using very complex logic.  Read more about this parsing logic here(Link to Parse Date article for RadMaskedEditBox)
      

The embedded text editor of RadTimePicker is RadMaskedEditBox. So if you want to take the advantages from new DateTime parsing logic the only thing that you should to do is to change the MaskType of embedded editor.
      

#### __[C#]__

{{source=..\SamplesCS\Editors\TimePicker1.cs region=FreeFormDateTimeTimePicker}}
	            
	            this.radTimePicker1.TimePickerElement.MaskedEditBox.MaskType = MaskType.FreeFormDateTime;
	
	{{endregion}}



#### __[VB.NET]__

{{source=..\SamplesVB\Editors\TimePicker1.vb region=FreeFormDateTimeTimePicker}}
	
	        Me.RadTimePicker1.TimePickerElement.MaskedEditBox.MaskType = MaskType.FreeFormDateTime
	
	{{endregion}}



## 