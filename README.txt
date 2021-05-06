README:  (Morris) Conclusion

成功將特定日子範圍內的event 寫入dbo.GAL_Event
e.g.
currentHref = "/api/events?pos=" + dr["id"].ToString() + "&previous=False&top=1000&after=2020-12-31Z&before=2021-05-06Z"
日子範圍由2020-12-31 至 2021-05-06 		4126 event record 用大約1分10秒完成      無error出現


HKLandACS.cs  內有SQL Group up 的 methods

eventViewer.cs 內現有program 邏輯是每次拎1000條event 直到日子範圍所有event.Count (4126), 然後一次過寫入SQL Table   dbo.GAL_Event

另外加寫了另外邏輯(現在沒有用, comment了)是每次拎1000條event, 先將1000條event寫入SQL Table   dbo.GAL_Event, 然後再拎1000條event, 之後將1000條event寫入SQL Table, ......
