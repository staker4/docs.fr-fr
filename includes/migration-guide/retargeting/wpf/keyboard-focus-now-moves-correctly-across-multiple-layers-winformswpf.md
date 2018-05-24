### <a name="keyboard-focus-now-moves-correctly-across-multiple-layers-of-winformswpf-hosting"></a><span data-ttu-id="dead2-101">Le focus clavier se déplace désormais correctement entre plusieurs couches d’hébergement WinForms/WPF</span><span class="sxs-lookup"><span data-stu-id="dead2-101">Keyboard focus now moves correctly across multiple layers of WinForms/WPF hosting</span></span>

|   |   |
|---|---|
|<span data-ttu-id="dead2-102">Détails</span><span class="sxs-lookup"><span data-stu-id="dead2-102">Details</span></span>|<span data-ttu-id="dead2-103">Imaginez une application WPF qui héberge un contrôle WinForms hébergeant à son tour des contrôles WPF.</span><span class="sxs-lookup"><span data-stu-id="dead2-103">Consider a WPF application hosting a WinForms control which in turn hosts WPF controls.</span></span> <span data-ttu-id="dead2-104">Les utilisateurs peuvent être dans l’impossibilité de quitter la couche WinForms au moyen de la touche Tab si le premier ou dernier contrôle dans cette couche est le contrôle WPF <code>System.Windows.Forms.Integration.ElementHost</code>.</span><span class="sxs-lookup"><span data-stu-id="dead2-104">Users may not be able to tab out of the WinForms layer if the first or last control in that layer is the WPF <code>System.Windows.Forms.Integration.ElementHost</code>.</span></span> <span data-ttu-id="dead2-105">Ce changement résout ce problème, et les utilisateurs peuvent désormais quitter la couche WinForms au moyen de la touche Tab. Les applications automatisées pour lesquelles il est indispensable que le focus ne quitte jamais la couche WinForms pourraient ne plus fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="dead2-105">This change fixes this issue, and users are now able to tab out of the WinForms layer.Automated applications that rely on focus never escaping the WinForms layer may no longer work as expected.</span></span>|
|<span data-ttu-id="dead2-106">Suggestion</span><span class="sxs-lookup"><span data-stu-id="dead2-106">Suggestion</span></span>|<span data-ttu-id="dead2-107">Un développeur qui souhaite utiliser ce changement tout en ciblant une version du .NET Framework antérieure à la version 4.7.2 peut définir l’ensemble suivant d’indicateurs AppContext sur false pour activer la modification.</span><span class="sxs-lookup"><span data-stu-id="dead2-107">A developer who wants to utilize this change while targeting a framework version below .NET 4.7.2 can set the following set of AppContext flags to false for the change to be enabled.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false;Switch.UseLegacyAccessibilityFeatures.2=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="dead2-108">Les applications WPF doivent accepter toutes les améliorations d’accessibilité antérieures pour obtenir les dernières améliorations.</span><span class="sxs-lookup"><span data-stu-id="dead2-108">WPF applications must opt in to all early accessibility improvements to get the later improvements.</span></span> <span data-ttu-id="dead2-109">En d’autres termes, les deux commutateurs <code>Switch.UseLegacyAccessibilityFeatures</code> et <code>Switch.UseLegacyAccessibilityFeatures.2</code> doivent être définis. Un développeur qui a besoin des fonctionnalités antérieures tout en ciblant .NET 4.7.2 ou version ultérieure peut définir l’indicateur AppContext suivant sur la valeur true pour activer la modification.</span><span class="sxs-lookup"><span data-stu-id="dead2-109">In other words, both the <code>Switch.UseLegacyAccessibilityFeatures</code> and the <code>Switch.UseLegacyAccessibilityFeatures.2</code> switches must be setA developer who requires the previous functionality while targeting .NET 4.7.2 or greater can set the following AppContext flag to true for the change to be disabled.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures.2=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="dead2-110">Portée</span><span class="sxs-lookup"><span data-stu-id="dead2-110">Scope</span></span>|<span data-ttu-id="dead2-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dead2-111">Edge</span></span>|
|<span data-ttu-id="dead2-112">Version</span><span class="sxs-lookup"><span data-stu-id="dead2-112">Version</span></span>|<span data-ttu-id="dead2-113">4.7.2</span><span class="sxs-lookup"><span data-stu-id="dead2-113">4.7.2</span></span>|
|<span data-ttu-id="dead2-114">Type</span><span class="sxs-lookup"><span data-stu-id="dead2-114">Type</span></span>|<span data-ttu-id="dead2-115">Reciblage</span><span class="sxs-lookup"><span data-stu-id="dead2-115">Retargeting</span></span>|
