---
uid: mvc/overview/older-versions/getting-started-with-aspnet-mvc3/vb/accessing-your-models-data-from-a-controller
title: 從控制器 (VB) 存取您的模型資料 |Microsoft Docs
author: Rick-Anderson
description: 本教學課程將教導您建置使用 Microsoft Visual Web Developer 2010 Express Service Pack 1，也就是 ASP.NET MVC Web 應用程式的基本概念...
ms.author: riande
ms.date: 01/12/2011
ms.assetid: cad00de1-3c68-4ff4-a436-54236d449459
msc.legacyurl: /mvc/overview/older-versions/getting-started-with-aspnet-mvc3/vb/accessing-your-models-data-from-a-controller
msc.type: authoredcontent
ms.openlocfilehash: 47d6e611ea79cf8c217f1f793d342b065233081f
ms.sourcegitcommit: 7b4e3936feacb1a8fcea7802aab3e2ea9c8af5b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2018
ms.locfileid: "48577882"
---
<a name="accessing-your-models-data-from-a-controller-vb"></a>從控制器 (VB) 存取您的模型資料
====================
藉由[Rick Anderson]((https://twitter.com/RickAndMSFT))

> 本教學課程將教導您建置使用 Microsoft Visual Web Developer 2010 Express Service Pack 1，也就是 Microsoft Visual Studio 的免費版本的 ASP.NET MVC Web 應用程式的基本概念。 在開始之前，請確定您已安裝符合下列先決條件。 您可以安裝所有人都按下列連結： [Web Platform Installer](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)。 或者，您可以個別安裝的必要條件，使用下列連結：
> 
> - [Visual Studio Web Developer Express SP1 必要條件](https://www.microsoft.com/web/gallery/install.aspx?appid=VWD2010SP1Pack)
> - [ASP.NET MVC 3 Tools Update](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=MVC3)
> - [SQL Server Compact 4.0](https://www.microsoft.com/web/gallery/install.aspx?appid=SQLCE;SQLCEVSTools_4_0)（執行階段 + 工具支援）
> 
> 如果您使用 Visual Studio 2010 而不 Visual Web Developer 2010，請按一下下列連結安裝必要的： [Visual Studio 2010 必要條件](https://www.microsoft.com/web/gallery/install.aspx?appsxml=&amp;appid=VS2010SP1Pack)。
> 
> 使用本主題隨附了 VB.NET 原始程式碼的 Visual Web Developer 專案。 [下載 VB.NET 版本](https://code.msdn.microsoft.com/Introduction-to-MVC-3-10d1b098)。 如果您偏好 C#，切換至[C# 版本](../cs/accessing-your-models-data-from-a-controller.md)本教學課程。


在本節中，您將建立新`MoviesController`類別，並撰寫程式碼會擷取電影資料，並顯示在瀏覽器中使用檢視範本。 請務必建置您的應用程式，再繼續進行。

以滑鼠右鍵按一下*控制器*資料夾，並建立新`MoviesController`控制站。 選取下列選項：

- 控制器名稱： **MoviesController**。 （這是預設值）。
- 範本：**使用 Entity Framework 與讀取/寫入動作和檢視、 控制器**。
- 模型類別： **Movie (MvcMovie.Models)**。
- 資料內容類別： **MovieDBContext (MvcMovie.Models)**。
- 檢視： **Razor (CSHTML)**。 （預設值。）

[![5addMovieController](accessing-your-models-data-from-a-controller/_static/image2.png)](accessing-your-models-data-from-a-controller/_static/image1.png)

按一下 [加入] 。 Visual Web Developer 會建立下列檔案和資料夾：

- *MoviesController.vb*專案中的檔案*控制器*資料夾。
- A*電影*在專案的資料夾*檢視*資料夾。
- *Create.vbhtml，Delete.vbhtml，Details.vbhtml，Edit.vbhtml*，並*Index.vbhtml*在新*Views\Movies*資料夾。

[![5_ScaffoldMovie](accessing-your-models-data-from-a-controller/_static/image4.png)](accessing-your-models-data-from-a-controller/_static/image3.png)

ASP.NET MVC 3 scaffolding 機制會自動建立 CRUD （建立、 讀取、 更新和刪除） 動作方法和您的檢視。 您現在有功能完整的 web 應用程式，可讓您建立、 列出、 編輯和刪除電影的項目。

執行應用程式，並瀏覽至`Movies`藉由附加的控制站 */Movies*至您的瀏覽器的網址列中的 URL。 因為應用程式依賴預設路由 (定義於*Global.asax*檔案)，瀏覽器要求`http://localhost:xxxxx/Movies`會路由傳送至預設`Index`動作方法的`Movies`控制站。 換句話說，瀏覽器要求`http://localhost:xxxxx/Movies`實際上是相同的瀏覽器要求`http://localhost:xxxxx/Movies/Index`。 因為您尚未加入任何尚未，結果會是空白的電影清單。

![](accessing-your-models-data-from-a-controller/_static/image5.png)

## <a name="creating-a-movie"></a>建立電影

選取 **Create New** 連結。 輸入電影相關的一些詳細資料，然後按一下**建立** 按鈕。

![](accessing-your-models-data-from-a-controller/_static/image6.png)

按一下 **建立**按鈕會使表單張貼至伺服器時，電影資訊儲存在資料庫中的位置。 若要將您再重新導向 */Movies* URL，您可以在其中看到新建立的電影清單中。

[![IndexWhenHarryMet](accessing-your-models-data-from-a-controller/_static/image8.png)](accessing-your-models-data-from-a-controller/_static/image7.png)

建立幾個電影項目。 嘗試 **Edit**、**Details** 和 **Delete** 連結，這些連結都可以正常運作。

## <a name="examining-the-generated-code"></a>檢查產生的程式碼

開啟*Controllers\MoviesController.vb*檔案，並檢查產生`Index`方法。 電影控制器的一部分`Index`方法如下所示。

[!code-vb[Main](accessing-your-models-data-from-a-controller/samples/sample1.vb)]

下面這行從`MoviesController`類別執行個體化的電影資料庫內容，如先前所述。 您可用於查詢、 編輯和刪除影片的電影資料庫內容。

[!code-vb[Main](accessing-your-models-data-from-a-controller/samples/sample2.vb)]

要求`Movies`控制器中的所有項目會傳回`Movies`電影資料庫資料表然後將結果傳送至`Index`檢視。

## <a name="strongly-typed-models-and-the-model-keyword"></a>強型別模型和@model關鍵字

稍早在本教學課程中，您看到如何控制器傳遞資料或物件給檢視範本中使用`ViewBag`物件。 `ViewBag`是動態的物件，提供便利的晚期繫結方式，將資訊傳遞至檢視。

ASP.NET MVC 也會提供能夠傳遞強型別資料或檢視範本的物件。 強型別方法可讓更佳編譯時間檢查您的程式碼和更豐富的 IntelliSense，Visual Web Developer 編輯器中。 我們使用這個方法和`MoviesController`類別以及*Index.vbhtml*檢視範本。

請注意程式碼的建立方式[ `List` ](https://msdn.microsoft.com/library/6sh2ey19.aspx)物件時它會呼叫`View`中的協助程式方法`Index`動作方法。 程式碼接著會傳遞這`Movies`從控制器到檢視的清單：

[!code-vb[Main](accessing-your-models-data-from-a-controller/samples/sample3.vb)]

藉由包括`@ModelType`陳述式在檢視範本檔案的頂端，您可以指定檢視預期要有的物件類型。 當您建立電影控制器時，Visual Web Developer 就會自動包含下列`@model`陳述式，在頂端*Index.vbhtml*檔案：

[!code-vbhtml[Main](accessing-your-models-data-from-a-controller/samples/sample4.vbhtml)]

這`@ModelType`指示詞可讓您存取控制器傳遞至檢視使用的電影清單`Model`強類型的物件。 例如，在*Index.vbhtml*範本，此程式碼迴圈電影透過操作`foreach`陳述式，透過強型別`Model`物件：

[!code-vbhtml[Main](accessing-your-models-data-from-a-controller/samples/sample5.vbhtml)]

因為`Model`物件已強類型 (為`IEnumerable<Movie>`物件)，每個`item`迴圈中的物件型別為`Movie`。 撇開其他優點，這表示您取得的程式碼的編譯時間檢查，並完整的程式碼編輯器中的 IntelliSense 支援：

[![5_Intellisense](accessing-your-models-data-from-a-controller/_static/image10.png)](accessing-your-models-data-from-a-controller/_static/image9.png)

## <a name="working-with-sql-server-compact"></a>使用 SQL Server Compact

Entity Framework Code First 偵測到所提供的資料庫連接字串指向`Movies`不存在，所以 Code First 資料庫自動建立的資料庫。 您可以確認它在查看已建立*應用程式\_資料*資料夾。 如果您沒有看到*Movies.sdf*檔案中，按一下**顯示所有檔案**按鈕**方案總管] 中**工具列上，按一下 [**重新整理**按鈕，然後再展開*應用程式\_資料*資料夾。

[![SDF_in_SolnExp](accessing-your-models-data-from-a-controller/_static/image12.png)](accessing-your-models-data-from-a-controller/_static/image11.png)

按兩下*Movies.sdf*來開啟**伺服器總管**。 然後展開**資料表**資料夾，以查看已在資料庫中建立的資料表。

> [!NOTE]
> 如果您收到錯誤，當您按兩下*Movies.sdf*，請確定您已安裝**Visual Studio 2010 SP1 Tools for SQL Server Compact 4.0**。 （如需軟體的連結，請參閱在本教學課程系列的第 1 部分中的必要條件清單）。如果您現在安裝版本，您必須關閉再重新開啟 Visual Web Developer。


[![DB_explorer](accessing-your-models-data-from-a-controller/_static/image14.png)](accessing-your-models-data-from-a-controller/_static/image13.png)

有兩個資料表，一個用於`Movie`實體集，然後`EdmMetadata`資料表。 `EdmMetadata`資料表由 Entity Framework 來判斷當模型和資料庫未同步。

以滑鼠右鍵按一下`Movies`資料表，然後選取**顯示資料表資料**以查看您所建立的資料。

[![MoviesTable](accessing-your-models-data-from-a-controller/_static/image16.png)](accessing-your-models-data-from-a-controller/_static/image15.png)

以滑鼠右鍵按一下`Movies`資料表，然後選取**編輯資料表結構描述**。

[![EditTableSchema](accessing-your-models-data-from-a-controller/_static/image18.png)](accessing-your-models-data-from-a-controller/_static/image17.png)

![TableSchemaSM](accessing-your-models-data-from-a-controller/_static/image19.png)

請注意如何的結構描述`Movies`資料表會對應至`Movie`您稍早建立的類別。 Entity Framework Code First 自動建立此結構描述根據您`Movie`類別。

當您完成時，關閉連線。 （如果您未關閉連接，您可能會發生錯誤的下次您執行專案）。

[![CloseConnection](accessing-your-models-data-from-a-controller/_static/image21.png)](accessing-your-models-data-from-a-controller/_static/image20.png)

您現在有資料庫和簡單的清單頁面，以顯示來自它的內容。 在下一個教學課程中，我們將檢查的 scaffold 程式碼的其餘部分，並新增`SearchIndex`方法和`SearchIndex`可讓您搜尋此資料庫中的電影的檢視。

> [!div class="step-by-step"]
> [上一頁](adding-a-model.md)
> [下一頁](examining-the-edit-methods-and-edit-view.md)
