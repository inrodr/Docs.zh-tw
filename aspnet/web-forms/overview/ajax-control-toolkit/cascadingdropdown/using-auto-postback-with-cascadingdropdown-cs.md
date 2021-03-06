---
uid: web-forms/overview/ajax-control-toolkit/cascadingdropdown/using-auto-postback-with-cascadingdropdown-cs
title: 使用自動回傳與 CascadingDropDown (C#) |Microsoft Docs
author: wenz
description: 在 AJAX Control Toolkit CascadingDropDown 控制擴充 DropDownList 控制項以讓一個 DropDownList 載入中的變更相關聯 anoth 中的值...
ms.author: riande
ms.date: 06/02/2008
ms.assetid: 6755d8d9-14be-4a1d-86e5-1a6110f3dea8
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/cascadingdropdown/using-auto-postback-with-cascadingdropdown-cs
msc.type: authoredcontent
ms.openlocfilehash: 7c84951691935d9976f961f65f96fa70633ecbce
ms.sourcegitcommit: 45ac74e400f9f2b7dbded66297730f6f14a4eb25
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/16/2018
ms.locfileid: "41831174"
---
<a name="using-auto-postback-with-cascadingdropdown-c"></a>使用自動回傳與 CascadingDropDown (C#)
====================
藉由[Christian Wenz](https://github.com/wenz)

[下載程式碼](http://download.microsoft.com/download/9/0/7/907760b1-2c60-4f81-aeb6-ca416a573b0d/cascadingdropdown3.cs.zip)或[下載 PDF](http://download.microsoft.com/download/2/d/c/2dc10e34-6983-41d4-9c08-f78f5387d32b/cascadingdropdown3CS.pdf)

> 在 AJAX Control Toolkit CascadingDropDown 控制擴充 DropDownList 控制項以讓一個 DropDownList 載入中的變更相關聯的另一個 DropDownList 中的值。 不過使用 CascadingDropDown 控制，ASP 時。NET 的 DropDownList 控制項的 AutoPostBack 功能無法運作，因為會以非同步方式將資料載入清單產生本身 （非必要） 回傳。 使用一些 JavaScript 程式碼中，您可以避免這種效果。


## <a name="overview"></a>總覽

在 AJAX Control Toolkit CascadingDropDown 控制擴充 DropDownList 控制項以讓一個 DropDownList 載入中的變更相關聯的另一個 DropDownList 中的值。 （比方說，一份清單會提供一份我們狀態，而且下一個清單則填入該狀態中主要城市）。不過使用 CascadingDropDown 控制，ASP 時。NET 的 DropDownList 控制項的 AutoPostBack 功能無法運作，因為會以非同步方式將資料載入清單產生本身 （非必要） 回傳。 使用一些 JavaScript 程式碼中，您可以避免這種效果。

## <a name="steps"></a>步驟

若要啟動的 ASP.NET AJAX Control Toolkit 中，功能`ScriptManager`控制項必須放置在任何位置上 (但內&lt; `form` &gt;項目):

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-cs/samples/sample1.aspx)]

DropDownList 控制項則需要：

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-cs/samples/sample2.aspx)]

此清單中，會加入 CascadingDropDown 擴充項，提供 web 服務 URL 和方法資訊：

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-cs/samples/sample3.aspx)]

CascadingDropDown extender 接著會以非同步方式呼叫 web 服務的下列方法簽章：

[!code-csharp[Main](using-auto-postback-with-cascadingdropdown-cs/samples/sample4.cs)]

方法會傳回類型 CascadingDropDown 值的陣列。 類型的建構函式必須要有先清單項目的標題，然後此值 (HTML`value`屬性)。

[!code-aspx[Main](using-auto-postback-with-cascadingdropdown-cs/samples/sample5.aspx)]

載入瀏覽器頁面，將會填滿下拉式清單中的，使用三個廠商，第二個要預先選取。 此外，ASP.NET 會定義`__doPostBack()`JavaScript 方法。 頁面載入之後，此 JavaScript 呼叫將會加入下拉式清單中，但只能有項目中。 如果在清單中不有任何項目，Control Toolkit 目前正在載入它們，讓 JavaScript 程式碼會使用逾時和在半秒後重新嘗試。

[!code-html[Main](using-auto-postback-with-cascadingdropdown-cs/samples/sample6.html)]

如此一來，當清單中有實際的項目，而且使用者選取一個項目只執行回傳。


[![選取清單項目造成回傳](using-auto-postback-with-cascadingdropdown-cs/_static/image2.png)](using-auto-postback-with-cascadingdropdown-cs/_static/image1.png)

選取清單項目造成回傳 ([按一下以檢視完整大小的影像](using-auto-postback-with-cascadingdropdown-cs/_static/image3.png))

> [!div class="step-by-step"]
> [上一頁](presetting-list-entries-with-cascadingdropdown-cs.md)
> [下一頁](filling-a-list-using-cascadingdropdown-vb.md)
