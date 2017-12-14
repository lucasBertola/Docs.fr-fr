---
uid: web-forms/overview/ajax-control-toolkit/collapsiblepanel/collapsing-and-expanding-a-panel-from-javascript-cs
title: "Réduire et développer un panneau de configuration à partir de JavaScript (c#) | Documents Microsoft"
author: wenz
description: "Le contrôle de CollapsiblePanel dans ASP.NET AJAX Control Toolkit étend un panneau de configuration et lui fournit la possibilité de réduire son contenu et le développer un..."
ms.author: aspnetcontent
manager: wpickett
ms.date: 06/02/2008
ms.topic: article
ms.assetid: de5500be-75e5-461a-8064-b70ae52ea6a4
ms.technology: dotnet-webforms
ms.prod: .net-framework
msc.legacyurl: /web-forms/overview/ajax-control-toolkit/collapsiblepanel/collapsing-and-expanding-a-panel-from-javascript-cs
msc.type: authoredcontent
ms.openlocfilehash: 666f3e212ccdd5b26b466f4672134ce751dc5dd1
ms.sourcegitcommit: 9a9483aceb34591c97451997036a9120c3fe2baf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2017
---
<a name="collapsing-and-expanding-a-panel-from-javascript-c"></a><span data-ttu-id="24f1c-103">Réduire et développer un panneau de configuration à partir de JavaScript (c#)</span><span class="sxs-lookup"><span data-stu-id="24f1c-103">Collapsing and Expanding a Panel from JavaScript (C#)</span></span>
====================
<span data-ttu-id="24f1c-104">par [Christian Wenz](https://github.com/wenz)</span><span class="sxs-lookup"><span data-stu-id="24f1c-104">by [Christian Wenz](https://github.com/wenz)</span></span>

<span data-ttu-id="24f1c-105">[Télécharger le Code](http://download.microsoft.com/download/8/a/a/8aab3c3e-de6f-463f-805c-5fda567eef6e/CollapsiblePanel1.cs.zip) ou [télécharger le PDF](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/collapsiblepanel1CS.pdf)</span><span class="sxs-lookup"><span data-stu-id="24f1c-105">[Download Code](http://download.microsoft.com/download/8/a/a/8aab3c3e-de6f-463f-805c-5fda567eef6e/CollapsiblePanel1.cs.zip) or [Download PDF](http://download.microsoft.com/download/b/6/a/b6ae89ee-df69-4c87-9bfb-ad1eb2b23373/collapsiblepanel1CS.pdf)</span></span>

> <span data-ttu-id="24f1c-106">Le contrôle de CollapsiblePanel dans ASP.NET AJAX Control Toolkit étend un panneau de configuration et lui fournit la possibilité de réduire son contenu et le développer à nouveau.</span><span class="sxs-lookup"><span data-stu-id="24f1c-106">The CollapsiblePanel control in the ASP.NET AJAX Control Toolkit extends a panel and provides it with the capability to collapse its contents and expand it again.</span></span> <span data-ttu-id="24f1c-107">Ces deux actions peuvent également être déclenchées à partir du code JavaScript personnalisé.</span><span class="sxs-lookup"><span data-stu-id="24f1c-107">These two actions can also be triggered from custom JavaScript code.</span></span>


## <a name="overview"></a><span data-ttu-id="24f1c-108">Vue d'ensemble</span><span class="sxs-lookup"><span data-stu-id="24f1c-108">Overview</span></span>

<span data-ttu-id="24f1c-109">Le contrôle de CollapsiblePanel dans ASP.NET AJAX Control Toolkit étend un panneau de configuration et lui fournit la possibilité de réduire son contenu et le développer à nouveau.</span><span class="sxs-lookup"><span data-stu-id="24f1c-109">The CollapsiblePanel control in the ASP.NET AJAX Control Toolkit extends a panel and provides it with the capability to collapse its contents and expand it again.</span></span> <span data-ttu-id="24f1c-110">Ces deux actions peuvent également être déclenchées à partir du code JavaScript personnalisé.</span><span class="sxs-lookup"><span data-stu-id="24f1c-110">These two actions can also be triggered from custom JavaScript code.</span></span>

## <a name="steps"></a><span data-ttu-id="24f1c-111">Étapes</span><span class="sxs-lookup"><span data-stu-id="24f1c-111">Steps</span></span>

<span data-ttu-id="24f1c-112">Tout d’abord, créez une page ASP.NET et inclure le `ScriptManager` les `<form>` élément.</span><span class="sxs-lookup"><span data-stu-id="24f1c-112">First of all, create a new ASP.NET page and include the `ScriptManager` within the one `<form>` element.</span></span> <span data-ttu-id="24f1c-113">Cette opération charge la bibliothèque ASP.NET AJAX, ce qui est requis par les outils de contrôle :</span><span class="sxs-lookup"><span data-stu-id="24f1c-113">This loads the ASP.NET AJAX library which is required by the Control Toolkit:</span></span>

[!code-aspx[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample1.aspx)]

<span data-ttu-id="24f1c-114">Ensuite, créez un panneau avec du texte afin que l’effet de la commande de réduction/développement peut être affichée :</span><span class="sxs-lookup"><span data-stu-id="24f1c-114">Then, create a panel with some text so that the collapse/expand effect can be seen:</span></span>

[!code-aspx[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample2.aspx)]

<span data-ttu-id="24f1c-115">Comme vous pouvez le voir, le panneau de configuration fait référence à une classe CSS qui est présentée ici (et fondamentalement définit une couleur d’arrière-plan et la largeur de son) :</span><span class="sxs-lookup"><span data-stu-id="24f1c-115">As you can see, the panel references a CSS class which is shown here (and basically defines a background color and the panel's width):</span></span>

[!code-css[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample3.css)]

<span data-ttu-id="24f1c-116">Le `CollapsiblePanelExtender` contrôle requiert le `TargetControlID` attribut afin que la boîte à outils sache quel panneau pour réduire ou développer à la demande :</span><span class="sxs-lookup"><span data-stu-id="24f1c-116">The `CollapsiblePanelExtender` control requires the `TargetControlID` attribute so that the toolkit knows which panel to collapse or expand upon request:</span></span>

[!code-aspx[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample4.aspx)]

<span data-ttu-id="24f1c-117">Malheureusement, l’extendeur actuellement n’expose pas une API spécifique pour réduire ou de développer le panneau de configuration, mais certaines méthodes non documentées effectuera.</span><span class="sxs-lookup"><span data-stu-id="24f1c-117">Unfortunately, the extender currently does not expose a specific API for collapsing or expanding the panel, but some undocumented methods will do.</span></span> <span data-ttu-id="24f1c-118">Tout d’abord, ajoutez trois boutons HTML à la page, ce qui déclenchera puis le JavaScript côté client pour réduire ou développer le contenu du panneau :</span><span class="sxs-lookup"><span data-stu-id="24f1c-118">First of all, add three HTML buttons to the page which will then trigger the client-side JavaScript to collapse or expand the panel's contents:</span></span>

[!code-aspx[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample5.aspx)]

<span data-ttu-id="24f1c-119">Dans le code JavaScript côté client (main `<script type="text/javascript">`), la `$find()` méthode doit être utilisée pour accéder à la `CollapsiblePanelExtender`.</span><span class="sxs-lookup"><span data-stu-id="24f1c-119">In the client-side JavaScript code (started with `<script type="text/javascript">`), the `$find()` method needs to be used to access the `CollapsiblePanelExtender`.</span></span> <span data-ttu-id="24f1c-120">`$find("cpe")`Retourne une référence à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="24f1c-120">`$find("cpe")` will return a reference to it.</span></span> <span data-ttu-id="24f1c-121">Ensuite, des méthodes spécifiques permettent de résoudre la tâche en cours.</span><span class="sxs-lookup"><span data-stu-id="24f1c-121">From there on, specific methods will solve the task at hand.</span></span>

<span data-ttu-id="24f1c-122">La méthode d’ouverture (développement), le panneau de configuration est appelée `_doOpen()`; le code suivant implémente la `doOpen()` fonction appelée lorsque le premier bouton est activé :</span><span class="sxs-lookup"><span data-stu-id="24f1c-122">The method for opening (expanding) the panel is called `_doOpen()`; the following code implements the `doOpen()` function called when the first button is clicked:</span></span>

[!code-javascript[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample6.js)]

<span data-ttu-id="24f1c-123">Pour la fermeture ou de réduire le panneau de configuration, le `_doClose()` (méthode) doit être exécutée.</span><span class="sxs-lookup"><span data-stu-id="24f1c-123">For closing, or collapsing the panel, the `_doClose()` method needs to be executed.</span></span> <span data-ttu-id="24f1c-124">Par conséquent, lorsque l’utilisateur clique sur le deuxième bouton, le code JavaScript suivant est appelé :</span><span class="sxs-lookup"><span data-stu-id="24f1c-124">So when the user clicks on the second button, the following JavaScript code is called:</span></span>

[!code-javascript[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample7.js)]

<span data-ttu-id="24f1c-125">Le troisième bouton bascule l’état du panneau : à partir de réduite en développée et vice versa.</span><span class="sxs-lookup"><span data-stu-id="24f1c-125">The third button toggles the state of the panel: from collapsed to expanded, and vice versa.</span></span> <span data-ttu-id="24f1c-126">Le `CollapsiblePanelExtender` expose le `toggle()` méthode savoir exactement : inverse l’état du panneau.</span><span class="sxs-lookup"><span data-stu-id="24f1c-126">The `CollapsiblePanelExtender` exposes the `toggle()` method which does exactly that: reverses the state of the panel.</span></span> <span data-ttu-id="24f1c-127">Toutefois, il existe également une autre approche (qui est utilisé en interne par le `toggle()` (méthode)) : le `get_Collapsed()` méthode de la `CollapsiblePanelExtender()` indique si le panneau est réduit ou non.</span><span class="sxs-lookup"><span data-stu-id="24f1c-127">However there is also another approach (which is internally used by the `toggle()` method): The `get_Collapsed()` method of the `CollapsiblePanelExtender()` tells us whether the panel is collapsed or not.</span></span> <span data-ttu-id="24f1c-128">Selon la valeur de retour de cette fonction, le panneau de configuration est alors soit développé (`_doOpen()` méthode) ou réduite (`_doClose()`) méthode :</span><span class="sxs-lookup"><span data-stu-id="24f1c-128">Depending on the return value of this function, the panel is then either expanded (`_doOpen()` method) or collapsed (`_doClose()`) method:</span></span>

[!code-javascript[Main](collapsing-and-expanding-a-panel-from-javascript-cs/samples/sample8.js)]


<span data-ttu-id="24f1c-129">[![Le troisième bouton modifie l’état du panneau : à partir de réduite en arrière et développé](collapsing-and-expanding-a-panel-from-javascript-cs/_static/image2.png)](collapsing-and-expanding-a-panel-from-javascript-cs/_static/image1.png)</span><span class="sxs-lookup"><span data-stu-id="24f1c-129">[![The third button changes the state of the panel: from collapsed to expanded and back](collapsing-and-expanding-a-panel-from-javascript-cs/_static/image2.png)](collapsing-and-expanding-a-panel-from-javascript-cs/_static/image1.png)</span></span>

<span data-ttu-id="24f1c-130">Le troisième bouton modifie l’état du panneau : à partir de réduite en arrière et développé ([cliquez pour afficher l’image en taille réelle](collapsing-and-expanding-a-panel-from-javascript-cs/_static/image3.png))</span><span class="sxs-lookup"><span data-stu-id="24f1c-130">The third button changes the state of the panel: from collapsed to expanded and back ([Click to view full-size image](collapsing-and-expanding-a-panel-from-javascript-cs/_static/image3.png))</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="24f1c-131">Next</span><span class="sxs-lookup"><span data-stu-id="24f1c-131">Next</span></span>](collapsing-and-expanding-a-panel-from-javascript-vb.md)