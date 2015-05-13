---
title: Localization Provider
page_title: Localization Provider
description: Localization Provider
slug: calendar-localization-localization-provider
tags: localization,provider
published: True
position: 5
---

# Localization Provider



To localize RadCalendar to display control text and messages in a specific language:

* All required classes for localization are defined in __Telerik.WinControls.UI__ namespace.
          

* Start by creating a descendant of the __CalendarLocalizationProvider__ class.
          

* Override the __GetLocalizedString(string id)__ method and provide a translation for the available strings. If a translation is not provided, the default value will be returned. This behavior is guaranteed by the call to the base __GetLocalizedString__ method in the __default__ clause of the __switch__ statement in the example.
          

## 

Below is a sample implementation of an English localization provider:
        

#### __[C#]__

{{source=..\SamplesCS\Calendar\Localization\LocalizationProvider.cs region=Localization}}
	    public class MyEnglishCalendarLocalizationProvider : CalendarLocalizationProvider
	    {
	        public override string GetLocalizedString(string id)
	        {
	            switch (id)
	            {
	                case CalendarStringId.CalendarClearButton:
	                    return "Close";
	                case CalendarStringId.CalendarTodayButton:
	                    return "Today";
	                default:
	                    return base.GetLocalizedString(id);
	            }
	        }
	    }
	{{endregion}}



#### __[VB]__

{{source=..\SamplesVB\Calendar\Localization\LocalizationProvider.vb region=Localization}}
	Public Class MyEnglishCalendarLocalizationProvider
	    Inherits CalendarLocalizationProvider
	    Public Overrides Function GetLocalizedString(id As String) As String
	        Select Case id
	            Case CalendarStringId.CalendarClearButton
	                Return "Clear"
	            Case CalendarStringId.CalendarTodayButton
	                Return "Today"
	            Case Else
	                Return MyBase.GetLocalizedString(id)
	        End Select
	    End Function
	End Class
	{{endregion}}



To apply the custom localization provider, instantiate and assign it to the current localization provider: 

#### __[C#]__

{{source=..\SamplesCS\Calendar\Localization\LocalizationProvider.cs region=Usage}}
	            CalendarLocalizationProvider.CurrentProvider = new MyEnglishCalendarLocalizationProvider();
	{{endregion}}



#### __[VB]__

{{source=..\SamplesVB\Calendar\Localization\LocalizationProvider.vb region=Usage}}
	        CalendarLocalizationProvider.CurrentProvider = New MyEnglishCalendarLocalizationProvider()
	{{endregion}}

