---
title: "Présentation des pages Razor dans ASP.NET Core"
author: Rick-Anderson
description: "Ce document offre une vue d’ensemble de l’utilisation des pages Razor dans ASP.NET Core qui permet de faciliter le développement de scénarios orientés page."
keywords: ASP.NET Core, pages Razor
ms.author: riande
manager: wpickett
ms.date: 09/12/2017
ms.topic: get-started-article
ms.technology: aspnet
ms.prod: asp.net-core
uid: mvc/razor-pages/index
ms.openlocfilehash: a66b5ea32c2090b9944cd61f90f7fe011a823e82
ms.sourcegitcommit: 3511552becb081fb860a23d6c9b6c4efcab74577
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/07/2017
---
# <a name="introduction-to-razor-pages-in-aspnet-core"></a><span data-ttu-id="e271d-104">Présentation des pages Razor dans ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e271d-104">Introduction to Razor Pages in ASP.NET Core</span></span>

<span data-ttu-id="e271d-105">De [Rick Anderson](https://twitter.com/RickAndMSFT) et [Ryan Nowak](https://github.com/rynowak)</span><span class="sxs-lookup"><span data-stu-id="e271d-105">By [Rick Anderson](https://twitter.com/RickAndMSFT) and [Ryan Nowak](https://github.com/rynowak)</span></span>

<span data-ttu-id="e271d-106">Les pages Razor sont une nouvelle fonctionnalité d’ASP.NET Core MVC qui permet de développer des scénarios orientés page de façon plus simple et plus productive.</span><span class="sxs-lookup"><span data-stu-id="e271d-106">Razor Pages is a new feature of ASP.NET Core MVC that makes coding page-focused scenarios easier and more productive.</span></span>

<span data-ttu-id="e271d-107">Si vous avez besoin d’un didacticiel qui utilise l’approche Model-View-Controller, consultez [Bien démarrer avec ASP.NET Core MVC](xref:tutorials/first-mvc-app/start-mvc).</span><span class="sxs-lookup"><span data-stu-id="e271d-107">If you're looking for a tutorial that uses the Model-View-Controller approach, see [Getting started with ASP.NET Core MVC](xref:tutorials/first-mvc-app/start-mvc).</span></span>

<span data-ttu-id="e271d-108">Ce document fournit une introduction aux pages Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-108">This document provides an introduction to Razor Pages.</span></span> <span data-ttu-id="e271d-109">Il ne s’agit pas d’un didacticiel pas à pas.</span><span class="sxs-lookup"><span data-stu-id="e271d-109">It's not a step by step tutorial.</span></span> <span data-ttu-id="e271d-110">Si certaines sections vous semblent difficiles à suivre, consultez [Bien démarrer avec les pages Razor](xref:tutorials/razor-pages/razor-pages-start).</span><span class="sxs-lookup"><span data-stu-id="e271d-110">If you find some of the sections difficult to follow, see [Getting started with Razor Pages](xref:tutorials/razor-pages/razor-pages-start).</span></span>

<a name="prerequisites"></a>

## <a name="aspnet-core-20-prerequisites"></a><span data-ttu-id="e271d-111">Prérequis d’ASP.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e271d-111">ASP.NET Core 2.0 prerequisites</span></span>

<span data-ttu-id="e271d-112">Installez [.NET Core](https://www.microsoft.com/net/core) 2.0.0 ou ultérieur.</span><span class="sxs-lookup"><span data-stu-id="e271d-112">Install [.NET Core](https://www.microsoft.com/net/core) 2.0.0 or later.</span></span>

<span data-ttu-id="e271d-113">Si vous utilisez Visual Studio, installez [Visual Studio](https://www.visualstudio.com/vs/) 2017 version 15.3 ou ultérieure avec les charges de travail suivantes :</span><span class="sxs-lookup"><span data-stu-id="e271d-113">If you're using Visual Studio, install [Visual Studio](https://www.visualstudio.com/vs/) 2017 version 15.3 or later with the following workloads:</span></span>

* <span data-ttu-id="e271d-114">**Développement web et ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="e271d-114">**ASP.NET and web development**</span></span>
* <span data-ttu-id="e271d-115">**Développement multiplateforme .NET Core**</span><span class="sxs-lookup"><span data-stu-id="e271d-115">**.NET Core cross-platform development**</span></span>

<a name="rpvs17"></a>

## <a name="creating-a-razor-pages-project"></a><span data-ttu-id="e271d-116">Création d’un projet de pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-116">Creating a Razor Pages project</span></span>

# <a name="visual-studiotabvisual-studio"></a>[<span data-ttu-id="e271d-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e271d-117">Visual Studio</span></span>](#tab/visual-studio) 

<span data-ttu-id="e271d-118">Pour obtenir des instructions détaillées sur la façon de créer un projet de pages Razor avec Visual Studio, consultez [Bien démarrer avec les pages Razor](xref:tutorials/razor-pages/razor-pages-start).</span><span class="sxs-lookup"><span data-stu-id="e271d-118">See [Getting started with Razor Pages](xref:tutorials/razor-pages/razor-pages-start) for detailed instructions on how to create a Razor Pages project using Visual Studio.</span></span>

#   <a name="visual-studio-for-mactabvisual-studio-mac"></a>[<span data-ttu-id="e271d-119">Visual Studio pour Mac</span><span class="sxs-lookup"><span data-stu-id="e271d-119">Visual Studio for Mac</span></span>](#tab/visual-studio-mac)

<span data-ttu-id="e271d-120">Exécutez `dotnet new razor` à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e271d-120">Run `dotnet new razor` from the command line.</span></span>

<span data-ttu-id="e271d-121">Ouvrez le fichier *.csproj* généré à partir de Visual Studio pour Mac.</span><span class="sxs-lookup"><span data-stu-id="e271d-121">Open the generated *.csproj* file from Visual Studio for Mac.</span></span>

# <a name="visual-studio-codetabvisual-studio-code"></a>[<span data-ttu-id="e271d-122">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e271d-122">Visual Studio Code</span></span>](#tab/visual-studio-code) 

<span data-ttu-id="e271d-123">Exécutez `dotnet new razor` à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e271d-123">Run `dotnet new razor` from the command line.</span></span>

#   <a name="net-core-clitabnetcore-cli"></a>[<span data-ttu-id="e271d-124">CLI .NET Core</span><span class="sxs-lookup"><span data-stu-id="e271d-124">.NET Core CLI</span></span>](#tab/netcore-cli) 

<span data-ttu-id="e271d-125">Exécutez `dotnet new razor` à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="e271d-125">Run `dotnet new razor` from the command line.</span></span>

---

## <a name="razor-pages"></a><span data-ttu-id="e271d-126">Pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-126">Razor Pages</span></span>

<span data-ttu-id="e271d-127">La fonctionnalité Pages Razor est activée dans *Startup.cs* :</span><span class="sxs-lookup"><span data-stu-id="e271d-127">Razor Pages is enabled in *Startup.cs*:</span></span>

[!code-cs[main](index/sample/RazorPagesIntro/Startup.cs?name=snippet_Startup)]

<span data-ttu-id="e271d-128">Considérez une page de base : <a name="OnGet"></a></span><span class="sxs-lookup"><span data-stu-id="e271d-128">Consider a basic page: <a name="OnGet"></a></span></span>

[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Index.cshtml)]

<span data-ttu-id="e271d-129">Le code précédent ressemble beaucoup à un fichier vue Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-129">The preceding code looks a lot like a Razor view file.</span></span> <span data-ttu-id="e271d-130">Ce qui le rend différent est la directive `@page`.</span><span class="sxs-lookup"><span data-stu-id="e271d-130">What makes it different is the `@page` directive.</span></span> <span data-ttu-id="e271d-131">`@page` fait du fichier une action MVC, ce qui signifie qu’il gère les demandes directement, sans passer par un contrôleur.</span><span class="sxs-lookup"><span data-stu-id="e271d-131">`@page` makes the file into an MVC action - which means that it handles requests directly, without going through a controller.</span></span> <span data-ttu-id="e271d-132">`@page` doit être la première directive Razor sur une page.</span><span class="sxs-lookup"><span data-stu-id="e271d-132">`@page` must be the first Razor directive on a page.</span></span> <span data-ttu-id="e271d-133">`@page` affecte le comportement d’autres constructions Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-133">`@page` affects the behavior of other Razor constructs.</span></span>

<span data-ttu-id="e271d-134">Une page similaire, utilisant une classe `PageModel`, est illustrée dans les deux fichiers suivants.</span><span class="sxs-lookup"><span data-stu-id="e271d-134">A similar page, using a `PageModel` class, is shown in the following two files.</span></span> <span data-ttu-id="e271d-135">Le fichier *Pages/Index2.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-135">The *Pages/Index2.cshtml* file:</span></span>

[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Index2.cshtml)]

<span data-ttu-id="e271d-136">Le fichier « code-behind » *Pages/Index2.cshtml.cs* :</span><span class="sxs-lookup"><span data-stu-id="e271d-136">The *Pages/Index2.cshtml.cs* "code-behind" file:</span></span>

[!code-cs[main](index/sample/RazorPagesIntro/Pages/Index2.cshtml.cs)]

<span data-ttu-id="e271d-137">Par convention, le fichier de classe `PageModel` a le même nom que le fichier Page Razor, avec *.cs* en plus.</span><span class="sxs-lookup"><span data-stu-id="e271d-137">By convention, the `PageModel` class file has the same name as the Razor Page file with *.cs* appended.</span></span> <span data-ttu-id="e271d-138">Par exemple, la page Razor précédente est *Pages/Index2.cshtml*.</span><span class="sxs-lookup"><span data-stu-id="e271d-138">For example, the previous Razor Page is *Pages/Index2.cshtml*.</span></span> <span data-ttu-id="e271d-139">Le fichier contenant la classe `PageModel` se nomme *Pages/Index2.cshtml.cs*.</span><span class="sxs-lookup"><span data-stu-id="e271d-139">The file containing the `PageModel` class is named *Pages/Index2.cshtml.cs*.</span></span>

<span data-ttu-id="e271d-140">Les associations des chemins d’URL aux pages sont déterminées par l’emplacement de la page dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e271d-140">The associations of URL paths to pages are determined by the page's location in the file system.</span></span> <span data-ttu-id="e271d-141">Le tableau suivant montre un chemin Page Razor et l’URL correspondante :</span><span class="sxs-lookup"><span data-stu-id="e271d-141">The following table shows a Razor Page path and the matching URL:</span></span>

| <span data-ttu-id="e271d-142">Nom et chemin de fichier</span><span class="sxs-lookup"><span data-stu-id="e271d-142">File name and path</span></span>               | <span data-ttu-id="e271d-143">URL correspondante</span><span class="sxs-lookup"><span data-stu-id="e271d-143">matching URL</span></span> |
| ----------------- | ------------ |
| <span data-ttu-id="e271d-144">*/Pages/Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-144">*/Pages/Index.cshtml*</span></span> | <span data-ttu-id="e271d-145">`/` ou `/Index`</span><span class="sxs-lookup"><span data-stu-id="e271d-145">`/` or `/Index`</span></span> |
| <span data-ttu-id="e271d-146">*/Pages/Contact.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-146">*/Pages/Contact.cshtml*</span></span> | `/Contact` |
| <span data-ttu-id="e271d-147">*/Pages/Store/Contact.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-147">*/Pages/Store/Contact.cshtml*</span></span> | `/Store/Contact` |
| <span data-ttu-id="e271d-148">*/Pages/Store/Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-148">*/Pages/Store/Index.cshtml*</span></span> | <span data-ttu-id="e271d-149">`/Store` ou `/Store/Index`</span><span class="sxs-lookup"><span data-stu-id="e271d-149">`/Store` or `/Store/Index`</span></span> |

<span data-ttu-id="e271d-150">Remarques :</span><span class="sxs-lookup"><span data-stu-id="e271d-150">Notes:</span></span>

* <span data-ttu-id="e271d-151">Le runtime recherche les fichiers Pages Razor dans le dossier *Pages* par défaut.</span><span class="sxs-lookup"><span data-stu-id="e271d-151">The runtime looks for Razor Pages files in the *Pages* folder by default.</span></span>
* <span data-ttu-id="e271d-152">`Index` est la page par défaut quand une URL n’inclut pas de page.</span><span class="sxs-lookup"><span data-stu-id="e271d-152">`Index` is the default page when a URL doesn't include a page.</span></span>

## <a name="writing-a-basic-form"></a><span data-ttu-id="e271d-153">Écriture d’un formulaire de base</span><span class="sxs-lookup"><span data-stu-id="e271d-153">Writing a basic form</span></span>

<span data-ttu-id="e271d-154">Les fonctionnalités des pages Razor sont conçues pour simplifier les modèles courants utilisés avec les navigateurs web.</span><span class="sxs-lookup"><span data-stu-id="e271d-154">Razor Pages features are designed to make common patterns used with web browsers easy.</span></span> <span data-ttu-id="e271d-155">La [liaison de modèle](xref:mvc/models/model-binding), les [Tag Helpers](xref:mvc/views/tag-helpers/intro)et les assistances HTML *fonctionnent tous* avec les propriétés définies dans une classe Page Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-155">[Model binding](xref:mvc/models/model-binding), [Tag Helpers](xref:mvc/views/tag-helpers/intro), and HTML helpers all *just work* with the properties defined in a Razor Page class.</span></span> <span data-ttu-id="e271d-156">Considérez une page qui implémente un formulaire « Nous contacter » de base pour le modèle `Contact` :</span><span class="sxs-lookup"><span data-stu-id="e271d-156">Consider a page that implements a basic "contact us" form for the `Contact` model:</span></span>

<span data-ttu-id="e271d-157">Pour les exemples de ce document, le `DbContext` est initialisé dans le fichier [Startup.cs](https://github.com/aspnet/Docs/blob/master/aspnetcore/mvc/razor-pages/index/sample/RazorPagesContacts/Startup.cs#L15-L16).</span><span class="sxs-lookup"><span data-stu-id="e271d-157">For the samples in this document, the `DbContext` is initialized in the [Startup.cs](https://github.com/aspnet/Docs/blob/master/aspnetcore/mvc/razor-pages/index/sample/RazorPagesContacts/Startup.cs#L15-L16) file.</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Startup.cs?highlight=15-16)]

<span data-ttu-id="e271d-158">Le modèle de données :</span><span class="sxs-lookup"><span data-stu-id="e271d-158">The data model:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Data/Customer.cs)]

<span data-ttu-id="e271d-159">Le contexte de la base de données :</span><span class="sxs-lookup"><span data-stu-id="e271d-159">The db context:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Data/AppDbContext.cs)]

<span data-ttu-id="e271d-160">Le fichier vue *Pages/Create.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-160">The *Pages/Create.cshtml* view file:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Create.cshtml)]

<span data-ttu-id="e271d-161">Le fichier code-behind *Pages/Create.cshtml.cs* de la vue :</span><span class="sxs-lookup"><span data-stu-id="e271d-161">The *Pages/Create.cshtml.cs* code-behind file for the view:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=snippet_ALL)]

<span data-ttu-id="e271d-162">Par convention, la classe `PageModel` se nomme `<PageName>Model` et se trouve dans le même espace de noms que la page.</span><span class="sxs-lookup"><span data-stu-id="e271d-162">By convention, the `PageModel` class is called `<PageName>Model` and is in the same namespace as the page.</span></span>

<span data-ttu-id="e271d-163">La classe `PageModel` permet de séparer la logique d’une page de sa présentation.</span><span class="sxs-lookup"><span data-stu-id="e271d-163">The `PageModel` class allows separation of the logic of a page from its presentation.</span></span> <span data-ttu-id="e271d-164">Elle définit des gestionnaires de page pour les demandes envoyées à la page et les données utilisées pour l’afficher.</span><span class="sxs-lookup"><span data-stu-id="e271d-164">It defines page handlers for requests sent to the page and the data used to render the page.</span></span> <span data-ttu-id="e271d-165">Cette séparation permet de gérer les dépendances entre les pages au moyen de [l’injection de dépendances](xref:fundamentals/dependency-injection) et d’effectuer des [tests unitaires](xref:testing/razor-pages-testing) sur les pages.</span><span class="sxs-lookup"><span data-stu-id="e271d-165">This separation allows you to manage page dependencies through [dependency injection](xref:fundamentals/dependency-injection) and to [unit test](xref:testing/razor-pages-testing) the pages.</span></span>

<span data-ttu-id="e271d-166">La page a une *méthode de gestionnaire* `OnPostAsync`, qui s’exécute sur les requêtes `POST` (quand un utilisateur poste le formulaire).</span><span class="sxs-lookup"><span data-stu-id="e271d-166">The page has an `OnPostAsync` *handler method*, which runs on `POST` requests (when a user posts the form).</span></span> <span data-ttu-id="e271d-167">Vous pouvez ajouter des méthodes de gestionnaire pour n’importe quel verbe HTTP.</span><span class="sxs-lookup"><span data-stu-id="e271d-167">You can add handler methods for any HTTP verb.</span></span> <span data-ttu-id="e271d-168">Les gestionnaires les plus courants sont :</span><span class="sxs-lookup"><span data-stu-id="e271d-168">The most common handlers are:</span></span>

* <span data-ttu-id="e271d-169">`OnGet` pour initialiser l’état nécessaire pour la page.</span><span class="sxs-lookup"><span data-stu-id="e271d-169">`OnGet` to initialize state needed for the page.</span></span> <span data-ttu-id="e271d-170">Exemple [OnGet](#OnGet).</span><span class="sxs-lookup"><span data-stu-id="e271d-170">[OnGet](#OnGet) sample.</span></span>
* <span data-ttu-id="e271d-171">`OnPost` pour gérer les envois de formulaire.</span><span class="sxs-lookup"><span data-stu-id="e271d-171">`OnPost` to handle form submissions.</span></span>

<span data-ttu-id="e271d-172">Le suffixe de nommage `Async` est facultatif, mais souvent utilisé par convention pour les fonctions asynchrones.</span><span class="sxs-lookup"><span data-stu-id="e271d-172">The `Async` naming suffix is optional but is often used by convention for asynchronous functions.</span></span> <span data-ttu-id="e271d-173">Le code `OnPostAsync` dans l’exemple précédent est similaire à celui que vous écririez normalement dans un contrôleur.</span><span class="sxs-lookup"><span data-stu-id="e271d-173">The `OnPostAsync` code in the preceding example looks similar to what you would normally write in a controller.</span></span> <span data-ttu-id="e271d-174">Le code précédent est typique des pages Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-174">The preceding code is typical for Razor Pages.</span></span> <span data-ttu-id="e271d-175">La plupart des primitives MVC comme la [liaison de modèle](xref:mvc/models/model-binding), la [validation](xref:mvc/models/validation) et les résultats d’action sont partagées.</span><span class="sxs-lookup"><span data-stu-id="e271d-175">Most of the MVC primitives like [model binding](xref:mvc/models/model-binding), [validation](xref:mvc/models/validation), and action results are shared.</span></span>  <!-- Review: Ryan, can we get a list of what is shared and what isn't? -->

<span data-ttu-id="e271d-176">La méthode `OnPostAsync` précédente :</span><span class="sxs-lookup"><span data-stu-id="e271d-176">The previous `OnPostAsync` method:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=snippet_OnPostAsync)]

<span data-ttu-id="e271d-177">Le flux de base de `OnPostAsync` :</span><span class="sxs-lookup"><span data-stu-id="e271d-177">The basic flow of `OnPostAsync`:</span></span>

<span data-ttu-id="e271d-178">Recherchez les erreurs de validation.</span><span class="sxs-lookup"><span data-stu-id="e271d-178">Check for validation errors.</span></span>

*  <span data-ttu-id="e271d-179">S’il n’y a aucune erreur, enregistrez les données et redirigez.</span><span class="sxs-lookup"><span data-stu-id="e271d-179">If there are no errors, save the data and redirect.</span></span>
*  <span data-ttu-id="e271d-180">S’il y a des erreurs, réaffichez la page avec des messages de validation.</span><span class="sxs-lookup"><span data-stu-id="e271d-180">If there are errors, show the page again with validation messages.</span></span> <span data-ttu-id="e271d-181">La validation côté client est identique à celle des applications ASP.NET Core MVC traditionnelles.</span><span class="sxs-lookup"><span data-stu-id="e271d-181">Client-side validation is identical to traditional ASP.NET Core MVC applications.</span></span> <span data-ttu-id="e271d-182">Dans de nombreux cas, les erreurs de validation sont détectées sur le client et jamais envoyées au serveur.</span><span class="sxs-lookup"><span data-stu-id="e271d-182">In many cases, validation errors would be detected on the client, and never submitted to the server.</span></span>

<span data-ttu-id="e271d-183">Quand les données sont entrées correctement, la méthode de gestionnaire `OnPostAsync` appelle la méthode d’assistance `RedirectToPage` pour retourner une instance de `RedirectToPageResult`.</span><span class="sxs-lookup"><span data-stu-id="e271d-183">When the data is entered successfully, the `OnPostAsync` handler method calls the `RedirectToPage` helper method to return an instance of `RedirectToPageResult`.</span></span> <span data-ttu-id="e271d-184">`RedirectToPage` est un nouveau résultat d’action, semblable à `RedirectToAction` ou `RedirectToRoute`, mais personnalisé pour les pages.</span><span class="sxs-lookup"><span data-stu-id="e271d-184">`RedirectToPage` is a new action result, similar to `RedirectToAction` or `RedirectToRoute`, but customized for pages.</span></span> <span data-ttu-id="e271d-185">Dans l’exemple précédent, il redirige vers la page Index racine (`/Index`).</span><span class="sxs-lookup"><span data-stu-id="e271d-185">In the preceding sample, it redirects to the root Index page (`/Index`).</span></span> <span data-ttu-id="e271d-186">`RedirectToPage` est détaillé dans la section [Génération d’URL pour les pages](#url_gen).</span><span class="sxs-lookup"><span data-stu-id="e271d-186">`RedirectToPage` is detailed in the [URL generation for Pages](#url_gen) section.</span></span>

<span data-ttu-id="e271d-187">Quand le formulaire envoyé comporte des erreurs de validation (qui sont passées au serveur), la méthode de gestionnaire `OnPostAsync` appelle la méthode d’assistance `Page`.</span><span class="sxs-lookup"><span data-stu-id="e271d-187">When the submitted form has validation errors (that are passed to the server), the`OnPostAsync` handler method calls the `Page` helper method.</span></span> <span data-ttu-id="e271d-188">`Page` retourne une instance de `PageResult`.</span><span class="sxs-lookup"><span data-stu-id="e271d-188">`Page` returns an instance of `PageResult`.</span></span> <span data-ttu-id="e271d-189">Le retour de `Page` est similaire à la façon dont les actions dans les contrôleurs retournent `View`.</span><span class="sxs-lookup"><span data-stu-id="e271d-189">Returning `Page` is similar to how actions in controllers return `View`.</span></span> <span data-ttu-id="e271d-190">`PageResult` est le type de retour <!-- Review  --> par défaut pour une méthode de gestionnaire.</span><span class="sxs-lookup"><span data-stu-id="e271d-190">`PageResult` is the default <!-- Review  --> return type for a handler method.</span></span> <span data-ttu-id="e271d-191">Une méthode de gestionnaire qui retourne `void` restitue la page.</span><span class="sxs-lookup"><span data-stu-id="e271d-191">A handler method that returns `void` renders the page.</span></span>

<span data-ttu-id="e271d-192">La propriété `Customer` utilise l’attribut `[BindProperty]` pour accepter la liaison de modèle.</span><span class="sxs-lookup"><span data-stu-id="e271d-192">The `Customer` property uses `[BindProperty]` attribute to opt in to model binding.</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=snippet_PageModel&highlight=10-11)]

<span data-ttu-id="e271d-193">Par défaut, les pages Razor lient les propriétés uniquement avec les verbes non-GET.</span><span class="sxs-lookup"><span data-stu-id="e271d-193">Razor Pages, by default, bind properties only with non-GET verbs.</span></span> <span data-ttu-id="e271d-194">La liaison aux propriétés peut réduire la quantité de code à écrire.</span><span class="sxs-lookup"><span data-stu-id="e271d-194">Binding to properties can reduce the amount of code you have to write.</span></span> <span data-ttu-id="e271d-195">Elle réduit la quantité de code en utilisant la même propriété pour afficher les champs de formulaire (`<input asp-for="Customer.Name" />`) et accepter l’entrée.</span><span class="sxs-lookup"><span data-stu-id="e271d-195">Binding reduces code by using the same property to render form fields (`<input asp-for="Customer.Name" />`) and accept the input.</span></span>

<span data-ttu-id="e271d-196">La page d’accueil (*Index.cshtml*) :</span><span class="sxs-lookup"><span data-stu-id="e271d-196">The home page (*Index.cshtml*):</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Index.cshtml)]

<span data-ttu-id="e271d-197">Le fichier code-behind *Index.cshtml.cs* :</span><span class="sxs-lookup"><span data-stu-id="e271d-197">The code behind *Index.cshtml.cs* file:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Index.cshtml.cs)]

<span data-ttu-id="e271d-198">Le fichier *Index.cshtml* contient le balisage suivant pour créer un lien d’édition pour chaque contact :</span><span class="sxs-lookup"><span data-stu-id="e271d-198">The *Index.cshtml* file contains the following markup to create an edit link for each contact:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Index.cshtml?range=21)]

<span data-ttu-id="e271d-199">Le [tag helper d’ancre](xref:mvc/views/tag-helpers/builtin-th/anchor-tag-helper) a utilisé l’attribut [asp-route-{value}](xref:mvc/views/tag-helpers/builtin-th/anchor-tag-helper#route) pour générer un lien vers la page Edit.</span><span class="sxs-lookup"><span data-stu-id="e271d-199">The [Anchor Tag Helper](xref:mvc/views/tag-helpers/builtin-th/anchor-tag-helper) used the [asp-route-{value}](xref:mvc/views/tag-helpers/builtin-th/anchor-tag-helper#route) attribute to generate a link to the Edit page.</span></span> <span data-ttu-id="e271d-200">Le lien contient des données d’itinéraire avec l’ID de contact.</span><span class="sxs-lookup"><span data-stu-id="e271d-200">The link contains route data with the contact ID.</span></span> <span data-ttu-id="e271d-201">Par exemple, `http://localhost:5000/Edit/1`.</span><span class="sxs-lookup"><span data-stu-id="e271d-201">For example, `http://localhost:5000/Edit/1`.</span></span>

<span data-ttu-id="e271d-202">Le fichier *Pages/Edit.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-202">The *Pages/Edit.cshtml* file:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Edit.cshtml?highlight=1)]

<span data-ttu-id="e271d-203">La première ligne contient la directive `@page "{id:int}"`.</span><span class="sxs-lookup"><span data-stu-id="e271d-203">The first line contains the `@page "{id:int}"` directive.</span></span> <span data-ttu-id="e271d-204">La contrainte de routage `"{id:int}"` indique à la page qu’elle doit accepter les requêtes qui contiennent des données d’itinéraire `int`.</span><span class="sxs-lookup"><span data-stu-id="e271d-204">The routing constraint`"{id:int}"` tells the page to accept requests to the page that contain `int` route data.</span></span> <span data-ttu-id="e271d-205">Si une requête à la page ne contient de données d’itinéraire qui peuvent être converties en `int`, le runtime retourne une erreur HTTP 404 (introuvable).</span><span class="sxs-lookup"><span data-stu-id="e271d-205">If a request to the page doesn't contain route data that can be converted to an `int`, the runtime returns an HTTP 404 (not found) error.</span></span>

<span data-ttu-id="e271d-206">Le fichier *Pages/Edit.cshtml.cs* :</span><span class="sxs-lookup"><span data-stu-id="e271d-206">The *Pages/Edit.cshtml.cs* file:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Edit.cshtml.cs)]

<span data-ttu-id="e271d-207">Le fichier *Index.cshtml* contient également le balisage pour créer un bouton Supprimer pour chaque contact client :</span><span class="sxs-lookup"><span data-stu-id="e271d-207">The *Index.cshtml* file also contains markup to create a delete button for each customer contact:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Index.cshtml?range=22-23)]

<span data-ttu-id="e271d-208">Lorsque le bouton Supprimer est rendu en HTML, son `formaction` comprend des paramètres pour :</span><span class="sxs-lookup"><span data-stu-id="e271d-208">When the delete button is rendered in HTML, its `formaction` includes parameters for:</span></span>

* <span data-ttu-id="e271d-209">L’ID du contact client spécifié par l’attribut `asp-route-id`.</span><span class="sxs-lookup"><span data-stu-id="e271d-209">The customer contact ID specified by the `asp-route-id` attribute.</span></span>
* <span data-ttu-id="e271d-210">Le `handler` spécifié par l’attribut `asp-page-handler`.</span><span class="sxs-lookup"><span data-stu-id="e271d-210">The `handler` specified by the `asp-page-handler` attribute.</span></span>

<span data-ttu-id="e271d-211">Voici un exemple de bouton Supprimer rendu avec un ID de contact client de `1`:</span><span class="sxs-lookup"><span data-stu-id="e271d-211">Here is an example of a rendered delete button with a customer contact ID of `1`:</span></span>

```html
<button type="submit" formaction="/?id=1&amp;handler=delete">delete</button>
```

<span data-ttu-id="e271d-212">Quand le bouton est sélectionné, une demande `POST` de forumaire est envoyée au serveur.</span><span class="sxs-lookup"><span data-stu-id="e271d-212">When the button is selected, a form `POST` request is sent to the server.</span></span> <span data-ttu-id="e271d-213">Par convention, le nom de la méthode de gestionnaire est sélectionné en fonction de la valeur du paramètre `handler` conformément au schéma `OnPost[handler]Async`.</span><span class="sxs-lookup"><span data-stu-id="e271d-213">By convention, the name of the handler method is selected based the value of the `handler` parameter according to the scheme `OnPost[handler]Async`.</span></span>

<span data-ttu-id="e271d-214">Étant donné que le `handler` est `delete` dans cet exemple, la méthode de gestionnaire `OnPostDeleteAsync` est utilisée pour traiter la demande `POST`.</span><span class="sxs-lookup"><span data-stu-id="e271d-214">Because the `handler` is `delete` in this example, the `OnPostDeleteAsync` handler method is used to process the `POST` request.</span></span> <span data-ttu-id="e271d-215">Si `asp-page-handler` est défini avec une autre valeur, telle que `remove`, une méthode de gestionnaire de page avec le nom `OnPostRemoveAsync` est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e271d-215">If the `asp-page-handler` is set to a different value, such as `remove`, a page handler method with the name `OnPostRemoveAsync` is selected.</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Index.cshtml.cs?range=26-37)]

<span data-ttu-id="e271d-216">La méthode `OnPostDeleteAsync` :</span><span class="sxs-lookup"><span data-stu-id="e271d-216">The `OnPostDeleteAsync` method:</span></span>

* <span data-ttu-id="e271d-217">Accepte l’`id` de la chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="e271d-217">Accepts the `id` from the query string.</span></span>
* <span data-ttu-id="e271d-218">Interroge la base de données pour le contact client avec `FindAsync`.</span><span class="sxs-lookup"><span data-stu-id="e271d-218">Queries the database for the customer contact with `FindAsync`.</span></span>
* <span data-ttu-id="e271d-219">Si le contact client est trouvé, il est supprimé de la liste des contacts client.</span><span class="sxs-lookup"><span data-stu-id="e271d-219">If the customer contact is found, they're removed from the list of customer contacts.</span></span> <span data-ttu-id="e271d-220">La base de données est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="e271d-220">The database is updated.</span></span>
* <span data-ttu-id="e271d-221">Appelle `RedirectToPage` pour rediriger vers la page Index racine (`/Index`).</span><span class="sxs-lookup"><span data-stu-id="e271d-221">Calls `RedirectToPage` to redirect to the root Index page (`/Index`).</span></span>

<a name="xsrf"></a>

## <a name="xsrfcsrf-and-razor-pages"></a><span data-ttu-id="e271d-222">XSRF/CSRF et pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-222">XSRF/CSRF and Razor Pages</span></span>

<span data-ttu-id="e271d-223">Vous n’avez aucun code à écrire pour la [validation anti-contrefaçon](xref:security/anti-request-forgery).</span><span class="sxs-lookup"><span data-stu-id="e271d-223">You don't have to write any code for [antiforgery validation](xref:security/anti-request-forgery).</span></span> <span data-ttu-id="e271d-224">La validation et la génération de jetons anti-contrefaçon sont automatiquement incluses dans les pages Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-224">Antiforgery token generation and validation are automatically included in Razor Pages.</span></span>

<a name="layout"></a>
## <a name="using-layouts-partials-templates-and-tag-helpers-with-razor-pages"></a><span data-ttu-id="e271d-225">Utilisation de dispositions, partiels, modèles et Tag Helpers avec les pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-225">Using Layouts, partials, templates, and Tag Helpers with Razor Pages</span></span>

<span data-ttu-id="e271d-226">Les pages Razor fonctionnent avec toutes les fonctionnalités du moteur de vue Razor.</span><span class="sxs-lookup"><span data-stu-id="e271d-226">Pages work with all the features of the Razor view engine.</span></span> <span data-ttu-id="e271d-227">Les dispositions, partiels, modèles, Tag Helpers, *_ViewStart.cshtml* et *_ViewImports.cshtml* fonctionnent de la même façon que pour les vues Razor classiques.</span><span class="sxs-lookup"><span data-stu-id="e271d-227">Layouts, partials, templates, Tag Helpers, *_ViewStart.cshtml*, *_ViewImports.cshtml* work in the same way they do for conventional Razor views.</span></span>

<span data-ttu-id="e271d-228">Nous allons nettoyer un peu cette page en tirant parti de certaines de ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="e271d-228">Let's declutter this page by taking advantage of some of those features.</span></span>

<span data-ttu-id="e271d-229">Ajoutez une [page de disposition](xref:mvc/views/layout) à *Pages/_Layout.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-229">Add a [layout page](xref:mvc/views/layout) to *Pages/_Layout.cshtml*:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_LayoutSimple.cshtml)]

<span data-ttu-id="e271d-230">La [disposition](xref:mvc/views/layout) :</span><span class="sxs-lookup"><span data-stu-id="e271d-230">The [Layout](xref:mvc/views/layout):</span></span>

* <span data-ttu-id="e271d-231">Contrôle la disposition de chaque page (à moins que la page ne refuse la disposition).</span><span class="sxs-lookup"><span data-stu-id="e271d-231">Controls the layout of each page (unless the page opts out of layout).</span></span>
* <span data-ttu-id="e271d-232">Importe des structures HTML telles que JavaScript et les feuilles de style.</span><span class="sxs-lookup"><span data-stu-id="e271d-232">Imports HTML structures such as JavaScript and stylesheets.</span></span>

<span data-ttu-id="e271d-233">Pour plus d’informations, consultez [Page de disposition](xref:mvc/views/layout).</span><span class="sxs-lookup"><span data-stu-id="e271d-233">See [layout page](xref:mvc/views/layout) for more information.</span></span>

<span data-ttu-id="e271d-234">La propriété [Layout](xref:mvc/views/layout#specifying-a-layout) est définie dans *Pages/_ViewStart.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-234">The [Layout](xref:mvc/views/layout#specifying-a-layout) property is set in *Pages/_ViewStart.cshtml*:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewStart.cshtml)]

<span data-ttu-id="e271d-235">**Remarque :** La disposition est dans le dossier *Pages*.</span><span class="sxs-lookup"><span data-stu-id="e271d-235">**Note:** The layout is in the *Pages* folder.</span></span> <span data-ttu-id="e271d-236">Les pages recherchent d’autres vues (dispositions, modèles, partiels) hiérarchiquement, en commençant dans le même dossier que la page active.</span><span class="sxs-lookup"><span data-stu-id="e271d-236">Pages look for other views (layouts, templates, partials) hierarchically, starting in the same folder as the current page.</span></span> <span data-ttu-id="e271d-237">Une disposition dans le dossier *Pages* peut être utilisée à partir de n’importe quelle page Razor sous le dossier *Pages*.</span><span class="sxs-lookup"><span data-stu-id="e271d-237">A layout in the *Pages* folder can be used from any Razor page under the *Pages* folder.</span></span>

<span data-ttu-id="e271d-238">Nous vous recommandons de **ne pas** placer le fichier de disposition dans le dossier *Views/Shared*.</span><span class="sxs-lookup"><span data-stu-id="e271d-238">We recommend you **not** put the layout file in the *Views/Shared* folder.</span></span> <span data-ttu-id="e271d-239">*Views/Shared* est un modèle de vues MVC.</span><span class="sxs-lookup"><span data-stu-id="e271d-239">*Views/Shared* is an MVC views pattern.</span></span> <span data-ttu-id="e271d-240">Les pages Razor sont censées s’appuyer sur la hiérarchie des dossiers, pas sur les conventions de chemins.</span><span class="sxs-lookup"><span data-stu-id="e271d-240">Razor Pages are meant to rely on folder hierarchy, not path conventions.</span></span>

<span data-ttu-id="e271d-241">La recherche de vue à partir d’une page Razor inclut le dossier *Pages*.</span><span class="sxs-lookup"><span data-stu-id="e271d-241">View search from a Razor Page includes the *Pages* folder.</span></span> <span data-ttu-id="e271d-242">Les dispositions, modèles et partiels que vous utilisez avec les contrôleurs MVC et les vues Razor conventionnelles *fonctionnent simplement*.</span><span class="sxs-lookup"><span data-stu-id="e271d-242">The layouts, templates, and partials you're using with MVC controllers and conventional Razor views *just work*.</span></span>

<span data-ttu-id="e271d-243">Ajoutez un fichier *Pages/_ViewImports.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-243">Add a *Pages/_ViewImports.cshtml* file:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewImports.cshtml)]

<span data-ttu-id="e271d-244">`@namespace` est expliqué plus loin dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="e271d-244">`@namespace` is explained later in the tutorial.</span></span> <span data-ttu-id="e271d-245">La directive `@addTagHelper` permet de bénéficier des [Tag Helpers intégrés](xref:mvc/views/tag-helpers/builtin-th/Index) dans toutes les pages du dossier *Pages*.</span><span class="sxs-lookup"><span data-stu-id="e271d-245">The `@addTagHelper` directive brings in the [built-in Tag Helpers](xref:mvc/views/tag-helpers/builtin-th/Index) to all the pages in the *Pages* folder.</span></span>

<a name="namespace"></a>

<span data-ttu-id="e271d-246">Quand la directive `@namespace` est utilisée explicitement sur une page :</span><span class="sxs-lookup"><span data-stu-id="e271d-246">When the `@namespace` directive is used explicitly on a page:</span></span>

[!code-cshtml[main](index/sample/RazorPagesIntro/Pages/Customers/Namespace2.cshtml?highlight=2)]

<span data-ttu-id="e271d-247">La directive définit l’espace de noms pour la page.</span><span class="sxs-lookup"><span data-stu-id="e271d-247">The directive sets the namespace for the page.</span></span> <span data-ttu-id="e271d-248">La directive `@model` n’a pas besoin d’inclure l’espace de noms.</span><span class="sxs-lookup"><span data-stu-id="e271d-248">The `@model` directive doesn't need to include the namespace.</span></span>

<span data-ttu-id="e271d-249">Quand la directive `@namespace` est contenue dans *_ViewImports.cshtml*, l’espace de noms spécifié fournit le préfixe de l’espace de noms généré dans la Page qui importe la directive `@namespace`.</span><span class="sxs-lookup"><span data-stu-id="e271d-249">When the `@namespace` directive is contained in *_ViewImports.cshtml*, the specified namespace supplies the prefix for the generated namespace in the Page that imports the `@namespace` directive.</span></span> <span data-ttu-id="e271d-250">Le reste de l’espace de noms généré (la partie suffixe) est le chemin relatif séparé par un point entre le dossier contenant *_ViewImports.cshtml* et le dossier contenant la page.</span><span class="sxs-lookup"><span data-stu-id="e271d-250">The rest of the generated namespace (the suffix portion) is the dot-separated relative path between the folder containing *_ViewImports.cshtml* and the folder containing the page.</span></span>

<span data-ttu-id="e271d-251">Par exemple, le fichier code-behind *Pages/Customers/Edit.cshtml.cs* définit explicitement l’espace de noms :</span><span class="sxs-lookup"><span data-stu-id="e271d-251">For example, the code behind file *Pages/Customers/Edit.cshtml.cs* explicitly sets the namespace:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/Edit.cshtml.cs?name=snippet_namespace)]

<span data-ttu-id="e271d-252">Le fichier *Pages/_ViewImports.cshtml* définit l’espace de noms suivant :</span><span class="sxs-lookup"><span data-stu-id="e271d-252">The *Pages/_ViewImports.cshtml* file sets the following namespace:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/_ViewImports.cshtml?highlight=1)]

<span data-ttu-id="e271d-253">L’espace de noms généré pour la page Razor *Pages/Customers/Edit.cshtml* est identique au fichier code-behind.</span><span class="sxs-lookup"><span data-stu-id="e271d-253">The generated namespace for the *Pages/Customers/Edit.cshtml* Razor Page is the same as the code behind file.</span></span> <span data-ttu-id="e271d-254">La directive `@namespace` a été conçue pour que les classes C# ajoutées à un projet et au code généré par les pages *fonctionnent simplement* sans avoir à ajouter de directive `@using` pour le fichier code-behind.</span><span class="sxs-lookup"><span data-stu-id="e271d-254">The `@namespace` directive was designed so the C# classes added to a project and pages-generated code *just work* without having to add an `@using` directive for the code behind file.</span></span>

<span data-ttu-id="e271d-255">**Remarque :** `@namespace` fonctionne également avec les vues Razor classiques.</span><span class="sxs-lookup"><span data-stu-id="e271d-255">**Note:** `@namespace` also works with conventional Razor views.</span></span>

<span data-ttu-id="e271d-256">Le fichier de vue *Pages/Create.cshtml* d’origine :</span><span class="sxs-lookup"><span data-stu-id="e271d-256">The original *Pages/Create.cshtml* view file:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts/Pages/Create.cshtml?highlight=2)]

<span data-ttu-id="e271d-257">Le fichier vue *Pages/Create.cshtml* mis à jour :</span><span class="sxs-lookup"><span data-stu-id="e271d-257">The updated *Pages/Create.cshtml* view file:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/Create.cshtml?highlight=2)]

<span data-ttu-id="e271d-258">Le [projet de démarrage de pages Razor](#rpvs17) contient *Pages/_ValidationScriptsPartial.cshtml*, qui connecte la validation côté client.</span><span class="sxs-lookup"><span data-stu-id="e271d-258">The [Razor Pages starter project](#rpvs17) contains the *Pages/_ValidationScriptsPartial.cshtml*, which hooks up client-side validation.</span></span>

<a name="url_gen"></a>

## <a name="url-generation-for-pages"></a><span data-ttu-id="e271d-259">Génération d’URL pour les pages</span><span class="sxs-lookup"><span data-stu-id="e271d-259">URL generation for Pages</span></span>

<span data-ttu-id="e271d-260">La page `Create`, illustrée précédemment, utilise `RedirectToPage` :</span><span class="sxs-lookup"><span data-stu-id="e271d-260">The `Create` page, shown previously, uses `RedirectToPage`:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/Pages/Create.cshtml.cs?name=snippet_OnPostAsync&highlight=10)]

<span data-ttu-id="e271d-261">L’application a la structure de fichiers/dossiers suivante :</span><span class="sxs-lookup"><span data-stu-id="e271d-261">The app has the following file/folder structure:</span></span>

* <span data-ttu-id="e271d-262">*/Pages*</span><span class="sxs-lookup"><span data-stu-id="e271d-262">*/Pages*</span></span>

  * <span data-ttu-id="e271d-263">*Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-263">*Index.cshtml*</span></span>
  * <span data-ttu-id="e271d-264">*/Customer*</span><span class="sxs-lookup"><span data-stu-id="e271d-264">*/Customer*</span></span>

    * <span data-ttu-id="e271d-265">*Create.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-265">*Create.cshtml*</span></span>
    * <span data-ttu-id="e271d-266">*Edit.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-266">*Edit.cshtml*</span></span>
    * <span data-ttu-id="e271d-267">*Index.cshtml*</span><span class="sxs-lookup"><span data-stu-id="e271d-267">*Index.cshtml*</span></span>

<span data-ttu-id="e271d-268">Une fois l’opération réussie, les pages *Pages/Customers/Create.cshtml* et *Pages/Customers/Edit.cshtml* redirigent vers *Pages/Index.cshtml*.</span><span class="sxs-lookup"><span data-stu-id="e271d-268">The *Pages/Customers/Create.cshtml* and *Pages/Customers/Edit.cshtml* pages redirect to *Pages/Index.cshtml* after success.</span></span> <span data-ttu-id="e271d-269">La chaîne `/Index` fait partie de l’URI pour accéder à la page précédente.</span><span class="sxs-lookup"><span data-stu-id="e271d-269">The string `/Index` is part of the URI to access the preceding page.</span></span> <span data-ttu-id="e271d-270">La chaîne `/Index` peut être utilisée pour générer l’URI de la page *Pages/Index.cshtml*.</span><span class="sxs-lookup"><span data-stu-id="e271d-270">The string `/Index` can be used to generate URIs to the *Pages/Index.cshtml* page.</span></span> <span data-ttu-id="e271d-271">Exemple :</span><span class="sxs-lookup"><span data-stu-id="e271d-271">For example:</span></span>

* `Url.Page("/Index", ...)`
* `<a asp-page="/Index">My Index Page</a>`
* `RedirectToPage("/Index")`

<span data-ttu-id="e271d-272">Le nom de la page est le chemin de la page à partir du dossier racine */Pages* (y compris un `/` de début, par exemple `/Index`).</span><span class="sxs-lookup"><span data-stu-id="e271d-272">The page name is the path to the page from the root */Pages* folder (including a leading `/`, for example `/Index`).</span></span> <span data-ttu-id="e271d-273">Les exemples de génération d’URL précédents sont beaucoup plus riches en fonctionnalités que le simple codage en dur d’une URL.</span><span class="sxs-lookup"><span data-stu-id="e271d-273">The preceding URL generation samples are much more feature rich than just hardcoding a URL.</span></span> <span data-ttu-id="e271d-274">La génération d’URL utilise le [routage](xref:mvc/controllers/routing) et peut générer et encoder des paramètres en fonction de la façon dont l’itinéraire est défini dans le chemin de destination.</span><span class="sxs-lookup"><span data-stu-id="e271d-274">URL generation uses [routing](xref:mvc/controllers/routing) and can generate and encode parameters according to how the route is defined in the destination path.</span></span>

<span data-ttu-id="e271d-275">La génération d’URL pour les pages prend en charge les noms relatifs.</span><span class="sxs-lookup"><span data-stu-id="e271d-275">URL generation for pages supports relative names.</span></span> <span data-ttu-id="e271d-276">Le tableau suivant montre la page Index sélectionnée avec différents paramètres `RedirectToPage` à partir de *Pages/Customers/Create.cshtml* :</span><span class="sxs-lookup"><span data-stu-id="e271d-276">The following table shows which Index page is selected with different `RedirectToPage` parameters from *Pages/Customers/Create.cshtml*:</span></span>

| <span data-ttu-id="e271d-277">RedirectToPage(x)</span><span class="sxs-lookup"><span data-stu-id="e271d-277">RedirectToPage(x)</span></span>| <span data-ttu-id="e271d-278">Page</span><span class="sxs-lookup"><span data-stu-id="e271d-278">Page</span></span> |
| ----------------- | ------------ |
| <span data-ttu-id="e271d-279">RedirectToPage("/Index")</span><span class="sxs-lookup"><span data-stu-id="e271d-279">RedirectToPage("/Index")</span></span> | <span data-ttu-id="e271d-280">*Pages/Index*</span><span class="sxs-lookup"><span data-stu-id="e271d-280">*Pages/Index*</span></span> |
| <span data-ttu-id="e271d-281">RedirectToPage("./Index");</span><span class="sxs-lookup"><span data-stu-id="e271d-281">RedirectToPage("./Index");</span></span> | <span data-ttu-id="e271d-282">*Pages/Customers/Index*</span><span class="sxs-lookup"><span data-stu-id="e271d-282">*Pages/Customers/Index*</span></span> |
| <span data-ttu-id="e271d-283">RedirectToPage("../Index")</span><span class="sxs-lookup"><span data-stu-id="e271d-283">RedirectToPage("../Index")</span></span> | <span data-ttu-id="e271d-284">*Pages/Index*</span><span class="sxs-lookup"><span data-stu-id="e271d-284">*Pages/Index*</span></span> |
| <span data-ttu-id="e271d-285">RedirectToPage("Index")</span><span class="sxs-lookup"><span data-stu-id="e271d-285">RedirectToPage("Index")</span></span>  | <span data-ttu-id="e271d-286">*Pages/Customers/Index*</span><span class="sxs-lookup"><span data-stu-id="e271d-286">*Pages/Customers/Index*</span></span> |

<span data-ttu-id="e271d-287">`RedirectToPage("Index")`, `RedirectToPage("./Index")` et `RedirectToPage("../Index")` sont des *noms relatifs*.</span><span class="sxs-lookup"><span data-stu-id="e271d-287">`RedirectToPage("Index")`, `RedirectToPage("./Index")`, and `RedirectToPage("../Index")`  are *relative names*.</span></span> <span data-ttu-id="e271d-288">Le paramètre `RedirectToPage` est *combiné* avec le chemin de la page active pour calculer le nom de la page de destination.</span><span class="sxs-lookup"><span data-stu-id="e271d-288">The `RedirectToPage` parameter is *combined* with the path of the current page to compute the name of the destination page.</span></span>  <!-- Review: Original had The provided string is combined with the page name of the current page to compute the name of the destination page. -- page name, not page path -->

<span data-ttu-id="e271d-289">La liaison de nom relatif est utile lors de la création de sites avec une structure complexe.</span><span class="sxs-lookup"><span data-stu-id="e271d-289">Relative name linking is useful when building sites with a complex structure.</span></span> <span data-ttu-id="e271d-290">Si vous utilisez des noms relatifs pour établir une liaison entre les pages d’un dossier, vous pouvez renommer ce dossier.</span><span class="sxs-lookup"><span data-stu-id="e271d-290">If you use relative names to link between pages in a folder, you can rename that folder.</span></span> <span data-ttu-id="e271d-291">Tous les liens fonctionneront encore (car ils n’incluent pas le nom du dossier).</span><span class="sxs-lookup"><span data-stu-id="e271d-291">All the links still work (because they didn't include the folder name).</span></span>

## <a name="tempdata"></a><span data-ttu-id="e271d-292">TempData</span><span class="sxs-lookup"><span data-stu-id="e271d-292">TempData</span></span>

<span data-ttu-id="e271d-293">ASP.NET Core expose la propriété [TempData](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.mvc.controller.tempdata?view=aspnetcore-2.0#Microsoft_AspNetCore_Mvc_Controller_TempData) sur un [contrôleur](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controller).</span><span class="sxs-lookup"><span data-stu-id="e271d-293">ASP.NET Core exposes the [TempData](https://docs.microsoft.com/en-us/dotnet/api/microsoft.aspnetcore.mvc.controller.tempdata?view=aspnetcore-2.0#Microsoft_AspNetCore_Mvc_Controller_TempData) property on a [controller](https://docs.microsoft.com/aspnet/core/api/microsoft.aspnetcore.mvc.controller).</span></span> <span data-ttu-id="e271d-294">Cette propriété stocke les données jusqu’à ce qu’elles soient lues.</span><span class="sxs-lookup"><span data-stu-id="e271d-294">This property stores data until it is read.</span></span> <span data-ttu-id="e271d-295">Vous pouvez utiliser les méthodes `Keep` et `Peek` pour examiner les données sans suppression.</span><span class="sxs-lookup"><span data-stu-id="e271d-295">The `Keep` and `Peek` methods can be used to examine the data without deletion.</span></span> <span data-ttu-id="e271d-296">`TempData` est utile pour la redirection, quand des données sont nécessaires pour plusieurs requêtes.</span><span class="sxs-lookup"><span data-stu-id="e271d-296">`TempData` is  useful for redirection, when data is needed for more than a single request.</span></span>

<span data-ttu-id="e271d-297">L’attribut `[TempData]` est une nouveauté dans ASP.NET Core 2.0. Il est pris en charge sur les contrôleurs et les pages.</span><span class="sxs-lookup"><span data-stu-id="e271d-297">The `[TempData]` attribute is new in ASP.NET Core 2.0 and is supported on controllers and pages.</span></span>

<span data-ttu-id="e271d-298">Le code suivant définit la valeur de `Message` à l’aide de `TempData` :</span><span class="sxs-lookup"><span data-stu-id="e271d-298">The following code sets the value of `Message` using `TempData`:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateDot.cshtml.cs?highlight=10-11,25&name=snippet_Temp)]

<span data-ttu-id="e271d-299">Le balisage suivant dans le fichier *Pages/Customers/Index.cshtml* affiche la valeur de `Message` à l’aide de `TempData`.</span><span class="sxs-lookup"><span data-stu-id="e271d-299">The following markup in the *Pages/Customers/Index.cshtml* file displays the value of `Message` using `TempData`.</span></span>

```cshtml
<h3>Msg: @Model.Message</h3>
```

<span data-ttu-id="e271d-300">Le fichier code-behind *Pages/Customers/Index.cshtml.cs* applique l’attribut `[TempData]` à la propriété `Message`.</span><span class="sxs-lookup"><span data-stu-id="e271d-300">The *Pages/Customers/Index.cshtml.cs* code-behind file applies the `[TempData]` attribute to the `Message` property.</span></span>

```cs
[TempData]
public string Message { get; set; }
```

<span data-ttu-id="e271d-301">Pour plus d’informations, consultez [TempData](xref:fundamentals/app-state#temp).</span><span class="sxs-lookup"><span data-stu-id="e271d-301">See [TempData](xref:fundamentals/app-state#temp) for more information.</span></span>

<a name="mhpp"></a>
## <a name="multiple-handlers-per-page"></a><span data-ttu-id="e271d-302">Plusieurs gestionnaires par page</span><span class="sxs-lookup"><span data-stu-id="e271d-302">Multiple handlers per page</span></span>

<span data-ttu-id="e271d-303">La page suivante génère un balisage pour deux gestionnaires de page à l’aide du Tag Helper `asp-page-handler` :</span><span class="sxs-lookup"><span data-stu-id="e271d-303">The following page generates markup for two page handlers using the `asp-page-handler` Tag Helper:</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml?highlight=12-13)]

<!-- Review: the FormActionTagHelper applies to all <form /> elements on a Razor page, even when there is no `asp-` attribute   -->

<span data-ttu-id="e271d-304">Le formulaire dans l’exemple précédent contient deux boutons d’envoi, chacun utilisant `FormActionTagHelper` pour envoyer à une URL différente.</span><span class="sxs-lookup"><span data-stu-id="e271d-304">The form in the preceding example has two submit buttons, each using the `FormActionTagHelper` to submit to a different URL.</span></span> <span data-ttu-id="e271d-305">L’attribut `asp-page-handler` est un complément de `asp-page`.</span><span class="sxs-lookup"><span data-stu-id="e271d-305">The `asp-page-handler` attribute is a companion to `asp-page`.</span></span> <span data-ttu-id="e271d-306">`asp-page-handler` génère des URL qui envoient à chacune des méthodes de gestionnaire définies par une page.</span><span class="sxs-lookup"><span data-stu-id="e271d-306">`asp-page-handler` generates URLs that submit to each of the handler methods defined by a page.</span></span> <span data-ttu-id="e271d-307">`asp-page` n’est pas spécifié, car l’exemple établit une liaison à la page active.</span><span class="sxs-lookup"><span data-stu-id="e271d-307">`asp-page` is not specified because the sample is linking to the current page.</span></span>

<span data-ttu-id="e271d-308">Le fichier code-behind :</span><span class="sxs-lookup"><span data-stu-id="e271d-308">The code-behind file:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml.cs?highlight=20,32)]

<span data-ttu-id="e271d-309">Le code précédent utilise des *méthodes de gestionnaire nommées*.</span><span class="sxs-lookup"><span data-stu-id="e271d-309">The preceding code uses *named handler methods*.</span></span> <span data-ttu-id="e271d-310">Pour créer des méthodes de gestionnaire nommées, il faut prendre le texte dans le nom après `On<HTTP Verb>` et avant `Async` (le cas échéant).</span><span class="sxs-lookup"><span data-stu-id="e271d-310">Named handler methods are created by taking the text in the name after `On<HTTP Verb>` and before `Async` (if present).</span></span> <span data-ttu-id="e271d-311">Dans l’exemple précédent, les méthodes de page sont OnPost**JoinList**Async et OnPost**JoinListUC**Async.</span><span class="sxs-lookup"><span data-stu-id="e271d-311">In the preceding example, the page methods are OnPost**JoinList**Async and OnPost**JoinListUC**Async.</span></span> <span data-ttu-id="e271d-312">Avec *OnPost* et *Async* supprimés, les noms des gestionnaires sont `JoinList` et `JoinListUC`.</span><span class="sxs-lookup"><span data-stu-id="e271d-312">With *OnPost* and *Async* removed, the handler names are `JoinList` and `JoinListUC`.</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateFATH.cshtml?range=12-13)]

<span data-ttu-id="e271d-313">Avec le code précédent, le chemin d’URL qui envoie à `OnPostJoinListAsync` est `http://localhost:5000/Customers/CreateFATH?handler=JoinList`.</span><span class="sxs-lookup"><span data-stu-id="e271d-313">Using the preceding code, the URL path that submits to `OnPostJoinListAsync` is `http://localhost:5000/Customers/CreateFATH?handler=JoinList`.</span></span> <span data-ttu-id="e271d-314">Le chemin d’URL qui envoie à `OnPostJoinListUCAsync` est `http://localhost:5000/Customers/CreateFATH?handler=JoinListUC`.</span><span class="sxs-lookup"><span data-stu-id="e271d-314">The URL path that submits to `OnPostJoinListUCAsync` is `http://localhost:5000/Customers/CreateFATH?handler=JoinListUC`.</span></span>

## <a name="customizing-routing"></a><span data-ttu-id="e271d-315">Personnalisation du routage</span><span class="sxs-lookup"><span data-stu-id="e271d-315">Customizing Routing</span></span>

<span data-ttu-id="e271d-316">Si vous ne voulez pas avoir la chaîne de requête `?handler=JoinList` dans l’URL, vous pouvez changer l’itinéraire pour placer le nom du gestionnaire dans la partie chemin de l’URL.</span><span class="sxs-lookup"><span data-stu-id="e271d-316">If you don't like the query string `?handler=JoinList` in the URL, you can change the route to put the handler name in the path portion of the URL.</span></span> <span data-ttu-id="e271d-317">Vous pouvez personnaliser l’itinéraire en ajoutant un modèle d’itinéraire placé entre des guillemets doubles après la directive `@page`.</span><span class="sxs-lookup"><span data-stu-id="e271d-317">You can customize the route by adding a route template enclosed in double quotes after the `@page` directive.</span></span>

[!code-cshtml[main](index/sample/RazorPagesContacts2/Pages/Customers/CreateRoute.cshtml?highlight=1)]

<span data-ttu-id="e271d-318">L’itinéraire précédent place le nom du gestionnaire dans le chemin d’URL au lieu de la chaîne de requête.</span><span class="sxs-lookup"><span data-stu-id="e271d-318">The preceding route puts the handler name in the URL path instead of the query string.</span></span> <span data-ttu-id="e271d-319">Le `?` suivant `handler` signifie que le paramètre d’itinéraire est facultatif.</span><span class="sxs-lookup"><span data-stu-id="e271d-319">The `?` following `handler` means the route parameter is optional.</span></span>

<span data-ttu-id="e271d-320">Vous pouvez utiliser `@page` pour ajouter des segments et des paramètres supplémentaires à l’itinéraire d’une page.</span><span class="sxs-lookup"><span data-stu-id="e271d-320">You can use `@page` to add additional segments and parameters to a page's route.</span></span> <span data-ttu-id="e271d-321">Tout ce qui y figure est **ajouté** à l’itinéraire par défaut de la page.</span><span class="sxs-lookup"><span data-stu-id="e271d-321">Whatever's there is **appended** to the default route of the page.</span></span> <span data-ttu-id="e271d-322">L’utilisation d’un chemin absolu ou virtuel pour changer l’itinéraire de la page (comme `"~/Some/Other/Path"`) n’est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="e271d-322">Using an absolute or virtual path to change the page's route (like `"~/Some/Other/Path"`) is not supported.</span></span>

## <a name="configuration-and-settings"></a><span data-ttu-id="e271d-323">Configuration et paramètres</span><span class="sxs-lookup"><span data-stu-id="e271d-323">Configuration and settings</span></span>

<span data-ttu-id="e271d-324">Pour configurer les options avancées, utilisez la méthode d’extension `AddRazorPagesOptions` sur le générateur MVC :</span><span class="sxs-lookup"><span data-stu-id="e271d-324">To configure advanced options, use the extension method `AddRazorPagesOptions` on the MVC builder:</span></span>

[!code-cs[main](index/sample/RazorPagesContacts/StartupAdvanced.cs?name=snippet_1)]

<span data-ttu-id="e271d-325">Actuellement, vous pouvez utiliser `RazorPagesOptions` pour définir le répertoire racine pour les pages, ou ajouter des conventions de modèle d’application pour les pages.</span><span class="sxs-lookup"><span data-stu-id="e271d-325">Currently you can use the `RazorPagesOptions` to set the root directory for pages, or add application model conventions for pages.</span></span> <span data-ttu-id="e271d-326">Nous permettrons à l’avenir une plus grande extensibilité en ce sens.</span><span class="sxs-lookup"><span data-stu-id="e271d-326">We'll enable more extensibility this way in the future.</span></span>

<span data-ttu-id="e271d-327">Pour précompiler des vues, consultez [Compilation de vue Razor](xref:mvc/views/view-compilation).</span><span class="sxs-lookup"><span data-stu-id="e271d-327">To precompile views, see [Razor view compilation](xref:mvc/views/view-compilation) .</span></span>

<span data-ttu-id="e271d-328">[Téléchargez ou affichez des exemples de code](https://github.com/aspnet/Docs/tree/master/aspnetcore/mvc/razor-pages/index/sample).</span><span class="sxs-lookup"><span data-stu-id="e271d-328">[Download or view sample code](https://github.com/aspnet/Docs/tree/master/aspnetcore/mvc/razor-pages/index/sample).</span></span>

<span data-ttu-id="e271d-329">Consultez [Bien démarrer avec les pages Razor dans ASP.NET Core](xref:tutorials/razor-pages/razor-pages-start), qui s’appuie sur cette introduction.</span><span class="sxs-lookup"><span data-stu-id="e271d-329">See [Getting started with Razor Pages in ASP.NET Core](xref:tutorials/razor-pages/razor-pages-start), which builds on this introduction.</span></span>

### <a name="specify-that-razor-pages-are-at-the-content-root"></a><span data-ttu-id="e271d-330">Spécifier que les pages Razor se trouvent à la racine du contenu</span><span class="sxs-lookup"><span data-stu-id="e271d-330">Specify that Razor Pages are at the content root</span></span>

<span data-ttu-id="e271d-331">Par défaut, les pages Razor sont associées à la racine */Pages*.</span><span class="sxs-lookup"><span data-stu-id="e271d-331">By default, Razor Pages are rooted in the */Pages* directory.</span></span> <span data-ttu-id="e271d-332">Ajoutez [WithRazorPagesAtContentRoot](/dotnet/api/microsoft.extensions.dependencyinjection.mvcrazorpagesmvcbuilderextensions.withrazorpagesatcontentroot) à [AddMvc](/dotnet/api/microsoft.extensions.dependencyinjection.mvcservicecollectionextensions.addmvc#Microsoft_Extensions_DependencyInjection_MvcServiceCollectionExtensions_AddMvc_Microsoft_Extensions_DependencyInjection_IServiceCollection_) pour spécifier que vos pages Razor se trouvent à la racine de contenu ([ContentRootPath](/dotnet/api/microsoft.aspnetcore.hosting.ihostingenvironment.contentrootpath)) de l’application :</span><span class="sxs-lookup"><span data-stu-id="e271d-332">Add [WithRazorPagesAtContentRoot](/dotnet/api/microsoft.extensions.dependencyinjection.mvcrazorpagesmvcbuilderextensions.withrazorpagesatcontentroot) to [AddMvc](/dotnet/api/microsoft.extensions.dependencyinjection.mvcservicecollectionextensions.addmvc#Microsoft_Extensions_DependencyInjection_MvcServiceCollectionExtensions_AddMvc_Microsoft_Extensions_DependencyInjection_IServiceCollection_) to specify that your Razor Pages are at the content root ([ContentRootPath](/dotnet/api/microsoft.aspnetcore.hosting.ihostingenvironment.contentrootpath)) of the app:</span></span>

```csharp
services.AddMvc()
    .AddRazorPagesOptions(options =>
    {
        ...
    })
    .WithRazorPagesAtContentRoot();
```

### <a name="specify-that-razor-pages-are-at-a-custom-root-directory"></a><span data-ttu-id="e271d-333">Spécifier que les pages Razor se trouvent dans un répertoire racine personnalisé</span><span class="sxs-lookup"><span data-stu-id="e271d-333">Specify that Razor Pages are at a custom root directory</span></span>

<span data-ttu-id="e271d-334">Ajoutez [WithRazorPagesRoot](/dotnet/api/microsoft.extensions.dependencyinjection.mvcrazorpagesmvccorebuilderextensions.withrazorpagesroot) à [AddMvc](/dotnet/api/microsoft.extensions.dependencyinjection.mvcservicecollectionextensions.addmvc#Microsoft_Extensions_DependencyInjection_MvcServiceCollectionExtensions_AddMvc_Microsoft_Extensions_DependencyInjection_IServiceCollection_) pour spécifier que vos pages Razor se trouvent dans le répertoire racine personnalisé de l’application (fournissez un chemin relatif) :</span><span class="sxs-lookup"><span data-stu-id="e271d-334">Add [WithRazorPagesRoot](/dotnet/api/microsoft.extensions.dependencyinjection.mvcrazorpagesmvccorebuilderextensions.withrazorpagesroot) to [AddMvc](/dotnet/api/microsoft.extensions.dependencyinjection.mvcservicecollectionextensions.addmvc#Microsoft_Extensions_DependencyInjection_MvcServiceCollectionExtensions_AddMvc_Microsoft_Extensions_DependencyInjection_IServiceCollection_) to specify that your Razor Pages are at a custom root directory in the app (provide a relative path):</span></span>

```csharp
services.AddMvc()
    .AddRazorPagesOptions(options =>
    {
        ...
    })
    .WithRazorPagesRoot("/path/to/razor/pages");
```

## <a name="see-also"></a><span data-ttu-id="e271d-335">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e271d-335">See also</span></span>

* [<span data-ttu-id="e271d-336">Bien démarrer avec les pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-336">Getting started with Razor Pages</span></span>](xref:tutorials/razor-pages/razor-pages-start)
* [<span data-ttu-id="e271d-337">Conventions d’autorisation des pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-337">Razor Pages authorization conventions</span></span>](xref:security/authorization/razor-pages-authorization)
* [<span data-ttu-id="e271d-338">Itinéraire personnalisé des pages Razor et fournisseurs de modèle de page</span><span class="sxs-lookup"><span data-stu-id="e271d-338">Razor Pages custom route and page model providers</span></span>](xref:mvc/razor-pages/razor-pages-convention-features)
* [<span data-ttu-id="e271d-339">Test unitaire et d’intégration des pages Razor</span><span class="sxs-lookup"><span data-stu-id="e271d-339">Razor Pages unit and integration testing</span></span>](xref:testing/razor-pages-testing)