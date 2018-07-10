<span data-ttu-id="4abdb-101">預設範本會建立 **RazorPagesMovie**、**Home**、**About** 和 **Contact** 連結和頁面。</span><span class="sxs-lookup"><span data-stu-id="4abdb-101">The default template creates **RazorPagesMovie**, **Home**, **About** and **Contact** links and pages.</span></span> <span data-ttu-id="4abdb-102">根據瀏覽器視窗的大小，您可能需要按一下瀏覽圖示來顯示連結。</span><span class="sxs-lookup"><span data-stu-id="4abdb-102">Depending on the size of your browser window, you might need to click the navigation icon to show the links.</span></span>

![Home 或 Index 頁面](~/tutorials/razor-pages/razor-pages-start/_static/home2.png)

<span data-ttu-id="4abdb-104">測試連結。</span><span class="sxs-lookup"><span data-stu-id="4abdb-104">Test the links.</span></span> <span data-ttu-id="4abdb-105">**RazorPagesMovie** 和 **Home** 連結會移至 Index 頁面。</span><span class="sxs-lookup"><span data-stu-id="4abdb-105">The **RazorPagesMovie** and **Home** links go to the Index page.</span></span> <span data-ttu-id="4abdb-106">**About** 和 **Contact** 連結則分別移至 `About` 和 `Contact` 頁面。</span><span class="sxs-lookup"><span data-stu-id="4abdb-106">The **About** and **Contact** links go to the `About` and `Contact` pages, respectively.</span></span>

## <a name="project-files-and-folders"></a><span data-ttu-id="4abdb-107">專案檔和資料夾</span><span class="sxs-lookup"><span data-stu-id="4abdb-107">Project files and folders</span></span>

<span data-ttu-id="4abdb-108">下表列出專案中的檔案和資料夾。</span><span class="sxs-lookup"><span data-stu-id="4abdb-108">The following table lists the files and folders in the project.</span></span> <span data-ttu-id="4abdb-109">在本教學課程中，*Startup.cs* 檔案是需要了解的最重要項目。</span><span class="sxs-lookup"><span data-stu-id="4abdb-109">For this tutorial, the *Startup.cs* file is the most important to understand.</span></span> <span data-ttu-id="4abdb-110">您不需要檢閱以下提供的每個連結。</span><span class="sxs-lookup"><span data-stu-id="4abdb-110">You don't need to review each link provided below.</span></span> <span data-ttu-id="4abdb-111">當您需要專案中的檔案或資料夾的詳細資訊時，便會提供連結作為參考。</span><span class="sxs-lookup"><span data-stu-id="4abdb-111">The links are provided as a reference when you need more information on a file or folder in the project.</span></span>

| <span data-ttu-id="4abdb-112">檔案或資料夾</span><span class="sxs-lookup"><span data-stu-id="4abdb-112">File or folder</span></span> | <span data-ttu-id="4abdb-113">用途</span><span class="sxs-lookup"><span data-stu-id="4abdb-113">Purpose</span></span> |
| -------------- | ------- |
| <span data-ttu-id="4abdb-114">*wwwroot*</span><span class="sxs-lookup"><span data-stu-id="4abdb-114">*wwwroot*</span></span> | <span data-ttu-id="4abdb-115">包含靜態資產。</span><span class="sxs-lookup"><span data-stu-id="4abdb-115">Contains static assets.</span></span> <span data-ttu-id="4abdb-116">請參閱[靜態檔案](xref:fundamentals/static-files)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-116">See [Static files](xref:fundamentals/static-files).</span></span> |
| <span data-ttu-id="4abdb-117">*頁面*</span><span class="sxs-lookup"><span data-stu-id="4abdb-117">*Pages*</span></span> | <span data-ttu-id="4abdb-118">[Razor 頁面](xref:razor-pages/index)的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4abdb-118">Folder for [Razor Pages](xref:razor-pages/index).</span></span> |
| <span data-ttu-id="4abdb-119">*appsettings.json*</span><span class="sxs-lookup"><span data-stu-id="4abdb-119">*appsettings.json*</span></span> | [<span data-ttu-id="4abdb-120">組態</span><span class="sxs-lookup"><span data-stu-id="4abdb-120">Configuration</span></span>](xref:fundamentals/configuration/index) |
| <span data-ttu-id="4abdb-121">*Program.cs*</span><span class="sxs-lookup"><span data-stu-id="4abdb-121">*Program.cs*</span></span> | <span data-ttu-id="4abdb-122">設定 ASP.NET Core 應用程式的[主機](xref:fundamentals/host/index)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-122">Configures the [host](xref:fundamentals/host/index) of the ASP.NET Core app.</span></span> |
| <span data-ttu-id="4abdb-123">*Startup.cs*</span><span class="sxs-lookup"><span data-stu-id="4abdb-123">*Startup.cs*</span></span> | <span data-ttu-id="4abdb-124">設定服務和要求管線。</span><span class="sxs-lookup"><span data-stu-id="4abdb-124">Configures services and the request pipeline.</span></span> <span data-ttu-id="4abdb-125">請參閱 [Startup](xref:fundamentals/startup)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-125">See [Startup](xref:fundamentals/startup).</span></span> |

### <a name="the-pagesshared-folder"></a><span data-ttu-id="4abdb-126">Pages/Shared 資料夾</span><span class="sxs-lookup"><span data-stu-id="4abdb-126">The Pages/Shared folder</span></span>

<span data-ttu-id="4abdb-127">*_Layout.cshtml* 檔案包含通用的 HTML 元素 (指令碼和樣式表連結)，並設定應用程式的配置。</span><span class="sxs-lookup"><span data-stu-id="4abdb-127">The *_Layout.cshtml* file contains common HTML elements (script and stylesheet links) and sets the layout for the app.</span></span> <span data-ttu-id="4abdb-128">例如，當您選取 **RazorPagesMovie**、**Home**、**About** 或 **Contact** 時，一組通用的元素就會出現在網頁中。</span><span class="sxs-lookup"><span data-stu-id="4abdb-128">For example when you select **RazorPagesMovie**, **Home**, **About** or **Contact**, a common set of elements appears in the webpage.</span></span> <span data-ttu-id="4abdb-129">通用元素包含頂端的導覽功能表和視窗底部的標頭。</span><span class="sxs-lookup"><span data-stu-id="4abdb-129">The common elements include the navigation menu at the top and the header at the bottom of the window.</span></span> <span data-ttu-id="4abdb-130">如需詳細資訊，請參閱[配置](xref:mvc/views/layout)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-130">For more information, see [Layout](xref:mvc/views/layout).</span></span>

<span data-ttu-id="4abdb-131">*_ValidationScriptsPartial.cshtml* 檔案提供 [jQuery](https://jquery.com/) 驗證指令碼的參考。</span><span class="sxs-lookup"><span data-stu-id="4abdb-131">The *_ValidationScriptsPartial.cshtml* file provides a reference to [jQuery](https://jquery.com/) validation scripts.</span></span> <span data-ttu-id="4abdb-132">稍後在教學課程中新增 `Create` 和 `Edit` 頁面時，會使用 *_ValidationScriptsPartial.cshtml* 檔案。</span><span class="sxs-lookup"><span data-stu-id="4abdb-132">When the `Create` and `Edit` pages are added later in the tutorial, the *_ValidationScriptsPartial.cshtml* file is used.</span></span>

<span data-ttu-id="4abdb-133">*_CookieConsentPartial.cshtml* 檔案會提供導覽列和內容來彙總隱私權和 Cookie 使用原則。</span><span class="sxs-lookup"><span data-stu-id="4abdb-133">The *_CookieConsentPartial.cshtml* file provides a navigation bar and content to summarize the privacy and cookie use policy.</span></span> <span data-ttu-id="4abdb-134">如需專案中所包含之 GDPR 資產的詳細資訊，請參閱 [ASP.NET Core 中的歐盟一般資料保護規定 (GDPR) 支援](xref:security/gdpr)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-134">For more information on the GDPR assets included in the project, see [EU General Data Protection Regulation (GDPR) support in ASP.NET Core)](xref:security/gdpr).</span></span>

### <a name="the-pages-folder"></a><span data-ttu-id="4abdb-135">Pages 資料夾</span><span class="sxs-lookup"><span data-stu-id="4abdb-135">The Pages folder</span></span>

<span data-ttu-id="4abdb-136">*_ViewStart.cshtml* 會設定 Razor 頁面 `Layout` 屬性，以使用 *_Layout.cshtml* 檔案。</span><span class="sxs-lookup"><span data-stu-id="4abdb-136">The *_ViewStart.cshtml* sets the Razor Pages `Layout` property to use the *_Layout.cshtml* file.</span></span> <span data-ttu-id="4abdb-137">如需詳細資訊，請參閱 [Layout](xref:mvc/views/layout)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-137">See [Layout](xref:mvc/views/layout) for more information.</span></span>

<span data-ttu-id="4abdb-138">*_ViewImports.cshtml* 檔案包含匯入至每個 Razor 頁面的 Razor 指示詞。</span><span class="sxs-lookup"><span data-stu-id="4abdb-138">The *_ViewImports.cshtml* file contains Razor directives that are imported into each Razor Page.</span></span> <span data-ttu-id="4abdb-139">如需詳細資訊，請參閱[匯入共用指示詞](xref:mvc/views/layout#importing-shared-directives)。</span><span class="sxs-lookup"><span data-stu-id="4abdb-139">See [Importing Shared Directives](xref:mvc/views/layout#importing-shared-directives) for more information.</span></span>

<span data-ttu-id="4abdb-140">`About`、`Contact` 和 `Index` 頁面是您可以用來啟動應用程式的基本頁面。</span><span class="sxs-lookup"><span data-stu-id="4abdb-140">The `About`, `Contact` and `Index` pages are basic pages you can use to start an app.</span></span> <span data-ttu-id="4abdb-141">`Error` 頁面則用來顯示錯誤資訊。</span><span class="sxs-lookup"><span data-stu-id="4abdb-141">The `Error` page is used to display error information.</span></span>