---
uid: single-page-application/overview/templates/breezeangular-template
title: "Modèle de jeu d’enfant/angulaire | Documents Microsoft"
author: madskristensen
description: "Modèle d’Application à Page unique est très simple/angulaire"
ms.author: aspnetcontent
manager: wpickett
ms.date: 03/08/2013
ms.topic: article
ms.assetid: db31e909-563a-4516-aadd-62aa210ac7e4
ms.technology: 
ms.prod: .net-framework
msc.legacyurl: /single-page-application/overview/templates/breezeangular-template
msc.type: authoredcontent
ms.openlocfilehash: faf28a510a83b7fa07585904344176601c2e1f34
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2017
---
<a name="breezeangular-template"></a><span data-ttu-id="ac477-103">Modèle de jeu d’enfant/angulaire</span><span class="sxs-lookup"><span data-stu-id="ac477-103">Breeze/Angular template</span></span>
====================
<span data-ttu-id="ac477-104">par [Mads Kristensen](https://github.com/madskristensen)</span><span class="sxs-lookup"><span data-stu-id="ac477-104">by [Mads Kristensen](https://github.com/madskristensen)</span></span>

> <span data-ttu-id="ac477-105">Le modèle MVC est très simple/angulaire a été écrit par Ward Bell</span><span class="sxs-lookup"><span data-stu-id="ac477-105">The Breeze/Angular MVC Template was written by Ward Bell</span></span>
> 
> [<span data-ttu-id="ac477-106">Téléchargez le modèle MVC est très simple/angulaire</span><span class="sxs-lookup"><span data-stu-id="ac477-106">Download the Breeze/Angular MVC Template</span></span>](https://go.microsoft.com/fwlink/?LinkId=286437)


<span data-ttu-id="ac477-107">[AngularJS](http://angularjs.org) est une bibliothèque open source à partir de Google pour la création d’Applications à Page unique (ZPS).</span><span class="sxs-lookup"><span data-stu-id="ac477-107">[AngularJS](http://angularjs.org) is an open source library from Google for building Single Page Applications (SPAs).</span></span> <span data-ttu-id="ac477-108">Il offre la liaison de données, l’injection de dépendances et la gestion de l’écran.</span><span class="sxs-lookup"><span data-stu-id="ac477-108">It offers data binding, dependency injection, and screen management.</span></span> <span data-ttu-id="ac477-109">Combiner avec [BreezeJS](http://www.breezejs.com/?utm_source=ms-spa), une autre bibliothèque open source pour la modélisation des données et gestion des données et que vous avez les composants essentiels pour une application client HTML/JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ac477-109">Combine it with [BreezeJS](http://www.breezejs.com/?utm_source=ms-spa), another open source library for data modeling and data management, and you have the essential ingredients for a great HTML/JavaScript client app.</span></span>

<span data-ttu-id="ac477-110">Le modèle est très simple/angulaire SPA est une variante de la [modèle de KnockoutJS SPA](../introduction/knockoutjs-template.md) inclus dans ASP.NET et Web Tools 2012.2 mise à jour.</span><span class="sxs-lookup"><span data-stu-id="ac477-110">The Breeze/Angular SPA template is a variation on the [KnockoutJS SPA template](../introduction/knockoutjs-template.md) included in the ASP.NET and Web Tools 2012.2 Update.</span></span> <span data-ttu-id="ac477-111">Si vous avez Visual Studio, vous aurez un exemple SPA en cours d’exécution en moins de 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="ac477-111">If you've got Visual Studio, you'll have an example SPA up and running in less than 60 seconds.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/NgRunningTodoPage.png)

<span data-ttu-id="ac477-112">L’aspect, l’application semble très similaire à celui du modèle KnockoutJS SPA.</span><span class="sxs-lookup"><span data-stu-id="ac477-112">Outwardly, the application looks the very similar to the KnockoutJS SPA template.</span></span> <span data-ttu-id="ac477-113">Mais il est très différente dans les coulisses.</span><span class="sxs-lookup"><span data-stu-id="ac477-113">But it's quite different under the hood.</span></span> <span data-ttu-id="ac477-114">Le modèle de KnockoutJS utilise Knockout pour la liaison de données et AJAX brute pour accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="ac477-114">The KnockoutJS template uses Knockout for data binding and raw AJAX for data access.</span></span> <span data-ttu-id="ac477-115">Le modèle est très simple/angulaire utilise angulaire pour la liaison de données et est très simple pour accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="ac477-115">The Breeze/Angular template uses Angular for data binding and Breeze for data access.</span></span> <span data-ttu-id="ac477-116">Ces bibliothèques activent des fonctionnalités supplémentaires, y compris l’historique et la navigation entre les pages.</span><span class="sxs-lookup"><span data-stu-id="ac477-116">These libaries enable additional capabilities, including page navigation and history.</span></span>

<span data-ttu-id="ac477-117">Voici la page de l’application sur :</span><span class="sxs-lookup"><span data-stu-id="ac477-117">Here is the application's About page:</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/NgRunningAboutPage.png)

<span data-ttu-id="ac477-118">Cette page affiche un journal des événements pendant la session active de l’utilisateur, y compris :</span><span class="sxs-lookup"><span data-stu-id="ac477-118">This page displays a running log of events during the current user session, including:</span></span>

- <span data-ttu-id="ac477-119">Pagination.</span><span class="sxs-lookup"><span data-stu-id="ac477-119">Paging.</span></span> <span data-ttu-id="ac477-120">Notez la création de contrôleur Todo #2 et #7.</span><span class="sxs-lookup"><span data-stu-id="ac477-120">Note the Todo controller creation at #2 and #7.</span></span>
- <span data-ttu-id="ac477-121">Requêtes distantes (n° 3) et les requêtes dans le cache local (#7).</span><span class="sxs-lookup"><span data-stu-id="ac477-121">Remote queries (#3) and local cache queries (#7).</span></span>
- <span data-ttu-id="ac477-122">Enregistrement de nouveau (n° 5, #6) et modifié les entités (n° 4).</span><span class="sxs-lookup"><span data-stu-id="ac477-122">Saving new (#5, #6) and modified (#4) entities.</span></span>
- <span data-ttu-id="ac477-123">Modifications validées sur le client (#9), afin de l’utilisateur peut corriger les erreurs avant de valider les modifications apportées à la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac477-123">Changes validated on the client (#9), so the user can correct mistakes before committing changes to the database.</span></span>

<span data-ttu-id="ac477-124">Il est plus à découvrir dans ce modèle, y compris :</span><span class="sxs-lookup"><span data-stu-id="ac477-124">There's more to explore in this template, including:</span></span>

- <span data-ttu-id="ac477-125">Chargement dynamique des modèles d’affichage HTML.</span><span class="sxs-lookup"><span data-stu-id="ac477-125">Dynamic loading of HTML view templates.</span></span>
- <span data-ttu-id="ac477-126">Liaison de données personnalisée via angulaire « directives ».</span><span class="sxs-lookup"><span data-stu-id="ac477-126">Custom data binding through Angular "directives."</span></span>
- <span data-ttu-id="ac477-127">Injection de dépendance et de modularité.</span><span class="sxs-lookup"><span data-stu-id="ac477-127">Modularity and dependency injection.</span></span>
- <span data-ttu-id="ac477-128">Filtres de requête trie, la pagination, projections et inclusion des entités associées.</span><span class="sxs-lookup"><span data-stu-id="ac477-128">Query filters, sorts, paging, projections, and inclusion of related entities.</span></span>
- <span data-ttu-id="ac477-129">Partage de données sur plusieurs écrans.</span><span class="sxs-lookup"><span data-stu-id="ac477-129">Sharing data across multiple screens.</span></span>
- <span data-ttu-id="ac477-130">L’enregistrement de plusieurs modifications comme une transaction unique.</span><span class="sxs-lookup"><span data-stu-id="ac477-130">Saving multiple changes as a single transaction.</span></span>
- <span data-ttu-id="ac477-131">Règles de validation propagées automatiquement à partir du serveur au client JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ac477-131">Validation rules propagated automatically from the server to the JavaScript client.</span></span>

<span data-ttu-id="ac477-132">Allons-y.</span><span class="sxs-lookup"><span data-stu-id="ac477-132">Let's get started.</span></span>

## <a name="create-a-breezeangular-template-project"></a><span data-ttu-id="ac477-133">Créer un projet de modèle est très simple/angulaire</span><span class="sxs-lookup"><span data-stu-id="ac477-133">Create a Breeze/Angular Template Project</span></span>

<span data-ttu-id="ac477-134">Téléchargez et installez le modèle en cliquant sur le bouton Télécharger ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="ac477-134">Download and install the template by clicking the Download button above.</span></span> <span data-ttu-id="ac477-135">Le modèle est empaqueté comme un fichier d’Extension Visual Studio (VSIX).</span><span class="sxs-lookup"><span data-stu-id="ac477-135">The template is packaged as a Visual Studio Extension (VSIX) file.</span></span> <span data-ttu-id="ac477-136">Vous devrez peut-être redémarrer Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ac477-136">You might need to restart Visual Studio.</span></span>

<span data-ttu-id="ac477-137">Dans le **modèles** volet, sélectionnez **modèles installés** et développez le **Visual C#** nœud.</span><span class="sxs-lookup"><span data-stu-id="ac477-137">In the **Templates** pane, select **Installed Templates** and expand the **Visual C#** node.</span></span> <span data-ttu-id="ac477-138">Sous **Visual C#**, sélectionnez **Web**.</span><span class="sxs-lookup"><span data-stu-id="ac477-138">Under **Visual C#**, select **Web**.</span></span> <span data-ttu-id="ac477-139">Dans la liste des modèles de projet, sélectionnez **ASP.NET MVC 4 Web Application**.</span><span class="sxs-lookup"><span data-stu-id="ac477-139">In the list of project templates, select **ASP.NET MVC 4 Web Application**.</span></span> <span data-ttu-id="ac477-140">Nommez le projet et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac477-140">Name the project and click **OK**.</span></span>

<span data-ttu-id="ac477-141">Dans le **nouveau projet** Assistant, sélectionnez **SPA angulaire du jeu d’enfant**.</span><span class="sxs-lookup"><span data-stu-id="ac477-141">In the **New Project** wizard, select **Breeze Angular SPA**.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/SelectBreezeNgSpaTemplate.png)

<span data-ttu-id="ac477-142">Appuyez sur Ctrl-F5 pour générer et exécuter l’application sans débogage, ou appuyez sur F5 pour exécuter avec débogage.</span><span class="sxs-lookup"><span data-stu-id="ac477-142">Press Ctrl-F5 to build and run the application without debugging, or press F5 to run with debugging.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ZephyrLogin.png)

<span data-ttu-id="ac477-143">Lorsque l’application s’exécute tout d’abord, il affiche un écran de connexion.</span><span class="sxs-lookup"><span data-stu-id="ac477-143">When the application first runs, it displays a login screen.</span></span> <span data-ttu-id="ac477-144">Cliquez sur le lien « Inscription » et une nouvelle page glides dans la vue, dans lequel vous pouvez entrer un nom d’utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ac477-144">Click the "Sign up" link and a new page glides into view, where you can enter a username and password.</span></span> <span data-ttu-id="ac477-145">(Les pages de connexion et d’inscription sont construites à l’aide d’ASP.NET MVC.) Quand vous envoyez le formulaire d’inscription, le serveur génère une liste des tâches avec deux éléments de votre compte.</span><span class="sxs-lookup"><span data-stu-id="ac477-145">(The login and registration pages are built using ASP.NET MVC.) When you submit the registration form, the server generates a TodoList with two items for your account.</span></span> <span data-ttu-id="ac477-146">Puis il les présente sur une note jaune.</span><span class="sxs-lookup"><span data-stu-id="ac477-146">Then it presents them to you on a yellow note.</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/TodoList.png)

<span data-ttu-id="ac477-147">Vous êtes maintenant dans la terre de SPA.</span><span class="sxs-lookup"><span data-stu-id="ac477-147">Now you are in the land of SPA.</span></span> <span data-ttu-id="ac477-148">Tout ce dont vous consultez et rencontrez lors de la manipulation de Todos est rendu et géré sur le client à l’aide de Knockout et est très simple.</span><span class="sxs-lookup"><span data-stu-id="ac477-148">Everything you see and experience while manipulating Todos is rendered and managed on the client with the help of Knockout and Breeze.</span></span> <span data-ttu-id="ac477-149">Explorer l’application en tant qu’utilisateur...</span><span class="sxs-lookup"><span data-stu-id="ac477-149">Explore the app as a user …</span></span> <span data-ttu-id="ac477-150">mais avec les yeux d’un développeur.</span><span class="sxs-lookup"><span data-stu-id="ac477-150">but with a developer's eye.</span></span> <span data-ttu-id="ac477-151">Utilisez les outils de développement dans votre navigateur pour capturer le trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="ac477-151">Use the developer tools in your browser to capture the network traffic.</span></span> <span data-ttu-id="ac477-152">(Dans Internet Explorer : appuyez sur F12, sélectionnez le **réseau** onglet, puis cliquez sur **démarrer la capture**.) Maintenant, essayez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="ac477-152">(In Internet Explorer: Press F12, select the **Network** tab, and click **Start capturing**.) Now try the following:</span></span>

- <span data-ttu-id="ac477-153">Ajouter un nouvel élément de tâche.</span><span class="sxs-lookup"><span data-stu-id="ac477-153">Add a new Todo item.</span></span>
- <span data-ttu-id="ac477-154">Cliquez sur l’étiquette et de modifier le titre de l’élément Todo</span><span class="sxs-lookup"><span data-stu-id="ac477-154">Click the label and edit the Todo item title</span></span>
- <span data-ttu-id="ac477-155">Cochez une case pour marquer l’élément terminé.</span><span class="sxs-lookup"><span data-stu-id="ac477-155">Check a checkbox to mark the item done.</span></span> <span data-ttu-id="ac477-156">Notez que la zone de texte est désactivé, le titre n’est plus modifiable.</span><span class="sxs-lookup"><span data-stu-id="ac477-156">Notice that the textbox is disabled, so the title is no longer editable.</span></span>
- <span data-ttu-id="ac477-157">Cliquez sur le « x » à droite de l’étiquette.</span><span class="sxs-lookup"><span data-stu-id="ac477-157">Click the ‘x' to the right of the label.</span></span> <span data-ttu-id="ac477-158">L’élément disparaît et est supprimé de la base de données.</span><span class="sxs-lookup"><span data-stu-id="ac477-158">The item disappears and is deleted from the database.</span></span>
- <span data-ttu-id="ac477-159">Choisissez un autre élément et effacer son titre.</span><span class="sxs-lookup"><span data-stu-id="ac477-159">Pick another item and clear its title.</span></span> <span data-ttu-id="ac477-160">Vous obtiendrez une erreur de validation que le titre est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ac477-160">You'll get a validation error that the title is required.</span></span> <span data-ttu-id="ac477-161">Après une brève pause, le titre de la précédent est restauré.</span><span class="sxs-lookup"><span data-stu-id="ac477-161">After a brief pause, the previous title is restored.</span></span>
- <span data-ttu-id="ac477-162">Tapez un titre ridiculement long.</span><span class="sxs-lookup"><span data-stu-id="ac477-162">Type in a ridiculously long title.</span></span> <span data-ttu-id="ac477-163">Vous obtiendrez une erreur de validation autre que le titre est trop long.</span><span class="sxs-lookup"><span data-stu-id="ac477-163">You'll get a different validation error that the title is too long.</span></span>
- <span data-ttu-id="ac477-164">Cliquez sur le bouton « Ajouter une liste Todo ».</span><span class="sxs-lookup"><span data-stu-id="ac477-164">Click the "Add Todo List" button.</span></span> <span data-ttu-id="ac477-165">Une nouvelle liste apparaît à gauche de la liste précédente.</span><span class="sxs-lookup"><span data-stu-id="ac477-165">A new list appears to the left of the previous list.</span></span>
- <span data-ttu-id="ac477-166">Manipuler le titre de TodoList, déclencher son requis et les validations de longueur.</span><span class="sxs-lookup"><span data-stu-id="ac477-166">Play with the TodoList title, triggering its required and length validations.</span></span>
- <span data-ttu-id="ac477-167">Cliquez dans la zone de texte titre pour effacer le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="ac477-167">Click in the title textbox to clear the error message.</span></span>
- <span data-ttu-id="ac477-168">Cliquez sur le « x » dans le cercle dans le coin supérieur droit pour supprimer la liste des tâches et ses todos.</span><span class="sxs-lookup"><span data-stu-id="ac477-168">Click the "x" in the circle in the upper right corner to delete the TodoList and its todos.</span></span>
- <span data-ttu-id="ac477-169">Cliquez sur le lien « About » dans le coin supérieur droit pour afficher un journal de ces activités.</span><span class="sxs-lookup"><span data-stu-id="ac477-169">Click the "About" link in the upper right to see a log of these activities.</span></span>

<span data-ttu-id="ac477-170">La logique de validation est effectuée côté client en un clin de œil.</span><span class="sxs-lookup"><span data-stu-id="ac477-170">The validation logic is performed client-side by Breeze.</span></span> <span data-ttu-id="ac477-171">Attributs de validation sur les classes de modèle de serveur sont propagées vers le client et exécutés automatiquement avant que le client contacte le serveur.</span><span class="sxs-lookup"><span data-stu-id="ac477-171">Validation attributes on the server model classes are propagated to the client and executed automatically before the client contacts the server.</span></span>

<span data-ttu-id="ac477-172">Examinez le trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="ac477-172">Review the network traffic.</span></span> <span data-ttu-id="ac477-173">Notez qu’il n’existait aucun appel au serveur lorsque le jeu d’enfant a détecté une erreur.</span><span class="sxs-lookup"><span data-stu-id="ac477-173">Notice that there were no calls to the server when Breeze detected an error.</span></span> <span data-ttu-id="ac477-174">Chaque modification valide a entraîné une demande POST sur « / api/tâches/SaveChanges ».</span><span class="sxs-lookup"><span data-stu-id="ac477-174">Each valid change resulted in a POST request to "/api/Todo/SaveChanges".</span></span> <span data-ttu-id="ac477-175">Est très simple regroupe les modifications et les envoie ensemble comme une demande unique pour le contrôleur d’API Web `SaveChanges` (méthode).</span><span class="sxs-lookup"><span data-stu-id="ac477-175">Breeze bundles the changes and sends them together as a single request to the Web API controller's `SaveChanges` method.</span></span> <span data-ttu-id="ac477-176">Qui est différent de modèle KockoutJS SPA, ce qui rend PUT, POST et supprimer des requêtes pour chaque élément individuellement.</span><span class="sxs-lookup"><span data-stu-id="ac477-176">That's different from KockoutJS SPA template, which makes PUT, POST, and DELETE requests for each item individually.</span></span>

<span data-ttu-id="ac477-177">En outre, ne notez aucun trafic réseau lorsque vous basculez entre la liste des tâches et sur les pages.</span><span class="sxs-lookup"><span data-stu-id="ac477-177">Also, notice there is no network traffic when you switch between the TodoList and About pages.</span></span> <span data-ttu-id="ac477-178">C’est parce que la requête a été limitée dans le cache local est très simple.</span><span class="sxs-lookup"><span data-stu-id="ac477-178">That's because the query has been constrained to the local Breeze cache.</span></span>

## <a name="peek-inside"></a><span data-ttu-id="ac477-179">Lire dans</span><span class="sxs-lookup"><span data-stu-id="ac477-179">Peek inside</span></span>

<span data-ttu-id="ac477-180">Cette application a un côté client et un côté serveur.</span><span class="sxs-lookup"><span data-stu-id="ac477-180">This application has a client side and a server side.</span></span> <span data-ttu-id="ac477-181">La pile côté client se compose de quelques HTML et une combinaison de modules de l’application JavaScript (dans le dossier « application ») ainsi que des bibliothèques JavaScript de tiers (dans le dossier « Scripts »).</span><span class="sxs-lookup"><span data-stu-id="ac477-181">The client-side stack consists of a little HTML and a combination of application JavaScript modules (in the "app" folder) plus third-party JavaScript libraries (in the "Scripts" folder).</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/NgClientArchitecture2.png)

<span data-ttu-id="ac477-182">L’architecture de l’interface utilisateur sépare les widgets HTML des vues à partir du code de présentation de prise en charge dans les contrôleurs.</span><span class="sxs-lookup"><span data-stu-id="ac477-182">The UI architecture separates the HTML widgets of the views from the supporting presentation code in the controllers.</span></span> <span data-ttu-id="ac477-183">Le système de liaison de données angulaire coordonne les vues et contrôleurs afin que chacun peut effectuer son travail sans une connaissance approfondie de l’autre.</span><span class="sxs-lookup"><span data-stu-id="ac477-183">The Angular data-binding system coordinates views and controllers so that each can do its job without intimate knowledge of the other.</span></span>

<span data-ttu-id="ac477-184">Le contrôleur de demande le contexte de données pour obtenir et enregistrer les entités du modèle.</span><span class="sxs-lookup"><span data-stu-id="ac477-184">The controller asks the data context to acquire and save the model entities.</span></span> <span data-ttu-id="ac477-185">Le contexte de données délègue la plupart du travail à est très simple, ce qui crée automatiquement le suivi des objets de modèle à partir des résultats de requête JSON.</span><span class="sxs-lookup"><span data-stu-id="ac477-185">The data context delegates most of the work to Breeze, which constructs self-tracking model objects from JSON query results.</span></span>

<span data-ttu-id="ac477-186">La pile côté serveur se compose d’un code de développeur et trois bibliothèques .NET de principe : Breeze.NET API Web et Entity Framework :</span><span class="sxs-lookup"><span data-stu-id="ac477-186">The server-side stack consists of some developer code and three principle .NET libraries: Web API, Entity Framework, and Breeze.NET:</span></span>

![](http://www.breezejs.com/sites/all/images/spa-template/ServerArchitecture.png)

<span data-ttu-id="ac477-187">L’architecture de base est la même que le modèle KockoutJS SPA.</span><span class="sxs-lookup"><span data-stu-id="ac477-187">The basic architecture is the same as the KockoutJS SPA template.</span></span> <span data-ttu-id="ac477-188">Toutefois, l’implémentation est beaucoup plus simple : les données ont été supprimées, et la plupart des détails de l’Entity Framework ont été déléguée à Breeze.NET.</span><span class="sxs-lookup"><span data-stu-id="ac477-188">However, the implementation is much simpler: The DTOs were deleted, and most of the Entity Framework details have been delegated to Breeze.NET.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ac477-189">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="ac477-189">Next Steps</span></span>

<span data-ttu-id="ac477-190">Nous vous suggérons d’Explorer le code, guidé par le [description détaillée](http://www.breezejs.com/ng-spa-template?utm_source=ms-spa) du client et les piles de serveur sur le site Web est très simple.</span><span class="sxs-lookup"><span data-stu-id="ac477-190">We suggest that you explore the code, guided by the [extensive discussion](http://www.breezejs.com/ng-spa-template?utm_source=ms-spa) of both the client and the server stacks on the Breeze website.</span></span>

<span data-ttu-id="ac477-191">Vous pouvez essayer de lecture de la requête du côté client est très simple. ajouter des filtres et les tris.</span><span class="sxs-lookup"><span data-stu-id="ac477-191">You might try playing with Breeze client-side query; add some filters and sorts.</span></span> <span data-ttu-id="ac477-192">Vous pouvez ajouter plusieurs propriétés de modèle et des entités supplémentaires pour obtenir une meilleure idée pour le développement de SPA de bout en bout.</span><span class="sxs-lookup"><span data-stu-id="ac477-192">You might add more model properties and more entities to get a better feel for end-to-end SPA development.</span></span> <span data-ttu-id="ac477-193">Lorsque vous êtes certain de la conception, vous pouvez supprimer les fonctionnalités de tâches et les remplacer par les vôtres.</span><span class="sxs-lookup"><span data-stu-id="ac477-193">When you are confident of the design, you can tear out the Todo features and replace them with your own.</span></span>

<span data-ttu-id="ac477-194">Bon développement !</span><span class="sxs-lookup"><span data-stu-id="ac477-194">Happy coding!</span></span>