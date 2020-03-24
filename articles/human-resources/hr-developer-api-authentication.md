---
title: Autenticação
description: Este artigo fornece informações gerais sobre como autenticar com a interface de programa aplicativo (API) do Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a0509ce99205d49d516e180203ffb65a1dc09a7c
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092097"
---
# <a name="authentication"></a><span data-ttu-id="dcb3d-103">Autenticação</span><span class="sxs-lookup"><span data-stu-id="dcb3d-103">Authentication</span></span>

<span data-ttu-id="dcb3d-104">Este artigo fornece informações gerais sobre como autenticar com a interface de programa aplicativo (API) do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-104">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="dcb3d-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="dcb3d-105">Overview</span></span>

<span data-ttu-id="dcb3d-106">A API de dados do Human Resources é uma implementação do OData.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-106">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="dcb3d-107">Para obter mais informações, consulte o [protocolo de dados abertos (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="dcb3d-107">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="dcb3d-108">Seu aplicativo deve ser autenticado como um chamador autorizado antes que a API atenda solicitações de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-108">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="dcb3d-109">Conceitos básicos</span><span class="sxs-lookup"><span data-stu-id="dcb3d-109">Fundamentals</span></span>

<span data-ttu-id="dcb3d-110">Para chamar a API de dados, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-110">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="dcb3d-111">O token de acesso contém informações sobre o seu aplicativo e a permissão que ele tem para chamar recursos no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-111">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="dcb3d-112">Token de acesso</span><span class="sxs-lookup"><span data-stu-id="dcb3d-112">Access token</span></span>

<span data-ttu-id="dcb3d-113">Os tokens de acesso emitidos pela plataforma de identidade da Microsoft são tokens da Web JSON (JavaScript Object Notation) codificados em base64 (JWTs).</span><span class="sxs-lookup"><span data-stu-id="dcb3d-113">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="dcb3d-114">Eles contêm informações (declarações) que a API de dados (e outras APIs da Web que são protegidas pela plataforma de identidade da Microsoft) utiliza para validar o chamador e verificar se o chamador tem as permissões corretas para executar a operação que está solicitando.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-114">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="dcb3d-115">Durante chamadas, você pode tratar tokens de acesso como opacos.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-115">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="dcb3d-116">Você deve sempre transmitir tokens de acesso por um canal seguro, como TLS (segurança da camada de transporte) e HTTPS (Hypertext Transfer Protocol Secure).</span><span class="sxs-lookup"><span data-stu-id="dcb3d-116">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="dcb3d-117">Este é um exemplo de um token de acesso que é emitido pela plataforma de identidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-117">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="dcb3d-118">Para chamar a API de dados, anexe o token de acesso como um token de portador ao cabeçalho de autorização na sua solicitação HTTP.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-118">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="dcb3d-119">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-119">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="dcb3d-120">Registre um novo aplicativo usando o portal do Azure</span><span class="sxs-lookup"><span data-stu-id="dcb3d-120">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="dcb3d-121">Entre no [portal do Microsoft Azure](https://portal.azure.com) com uma conta de trabalho ou escolar ou uma conta pessoal da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-121">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="dcb3d-122">Se a sua conta conceder acesso a mais de um locatário, selecione sua conta no canto superior direito e defina a sessão de portal para o locatário do Azure Active Directory (Azure AD) desejado.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-122">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="dcb3d-123">No painel esquerdo, selecione o serviço **Azure Active Directory** e, em seguida, **Registros de aplicativos \>Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-123">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="dcb3d-124">Quando a página **Registrar um aplicativo** for exibida, insira as informações de registro do seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="dcb3d-124">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="dcb3d-125">**Nome**: Insira um nome de aplicativo significativo que será mostrado aos usuários do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-125">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="dcb3d-126">**Tipos de conta com suporte**: selecione os tipos de contas aos quais seu aplicativo deve dar suporte.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-126">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="dcb3d-127">Tipos de conta compatíveis</span><span class="sxs-lookup"><span data-stu-id="dcb3d-127">Supported account types</span></span> | <span data-ttu-id="dcb3d-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="dcb3d-128">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="dcb3d-129">Contas neste diretório organizacional somente</span><span class="sxs-lookup"><span data-stu-id="dcb3d-129">Accounts in this organizational directory only</span></span> | <span data-ttu-id="dcb3d-130">Selecione esta opção se estiver criando um aplicativo de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-130">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="dcb3d-131">Esta opção não está disponível a menos que você esteja registrando o aplicativo em um diretório.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-131">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="dcb3d-132">Esta opção é mapeada somente para **Azure AD com um único locatário**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-132">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="dcb3d-133">Esta opção é padrão, a menos que você esteja registrando o aplicativo fora de um diretório.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-133">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="dcb3d-134">Nesse caso, a opção padrão é **Azure AD multilocatário e contas pessoais da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-134">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="dcb3d-135">Contas em qualquer diretório organizacional</span><span class="sxs-lookup"><span data-stu-id="dcb3d-135">Accounts in any organizational directory</span></span> | <span data-ttu-id="dcb3d-136">Selecione esta opção para direcionar todos os clientes comerciais e educacionais.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-136">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="dcb3d-137">Esta opção é mapeada somente para **Azure AD multilocatário**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-137">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="dcb3d-138">Se você tiver registrado o aplicativo como **Azure AD com um único locatário**, poderá usar o blade **Autenticação** para atualizá-lo com **Azure AD somente multilocatário** e voltar ao **Azure AD com um único locatário**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-138">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="dcb3d-139">Contas em qualquer diretório organizacional e contas pessoais da Microsoft</span><span class="sxs-lookup"><span data-stu-id="dcb3d-139">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="dcb3d-140">Selecione esta opção para direcionar o conjunto mais amplo de clientes.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-140">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="dcb3d-141">Esta opção é mapeada para **Azure AD multilocatário e contas pessoais da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-141">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="dcb3d-142">Se você tiver registrado o aplicativo como **Azure AD multilocatário e contas pessoais da Microsoft**, não poderá alterar essa configuração na interface do usuário (IU).</span><span class="sxs-lookup"><span data-stu-id="dcb3d-142">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="dcb3d-143">Em vez disso, você deve usar o editor de manifesto de aplicativo para alterar os tipos de conta com suporte.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-143">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="dcb3d-144">**Redirecionar URI (opcional)** – Selecione o tipo de aplicativo que você está criando: **Web** ou **cliente púbico (móvel e desktop)**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-144">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="dcb3d-145">Em seguida, insira o URI de redirecionamento (ou URL de resposta) para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-145">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="dcb3d-146">Para aplicativos Web, forneça a URL base do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-146">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="dcb3d-147">Por exemplo, `http://localhost:31544` pode ser a URL de um aplicativo Web executado no seu computador local.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-147">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="dcb3d-148">Os usuários utilizam esta URL para entrar em um aplicativo cliente Web.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-148">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="dcb3d-149">Para aplicativos de cliente público, forneça o URI que o Azure AD usa para retornar respostas de token.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-149">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="dcb3d-150">Insira um valor específico para seu aplicativo, como `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-150">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="dcb3d-151">Para ver exemplos específicos para aplicativos Web ou aplicativos nativos, consulte o início rápido na [plataforma de identidades da Microsoft (antes Azure Active Directory para desenvolvedores)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="dcb3d-151">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="dcb3d-152">Em **Permissões de API**, selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-152">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="dcb3d-153">Em seguida, na guia **APIs que minha organização utiliza**, procure o **Dynamics 365 Human Resources** e adicione a permissão **user\_impersonation** ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-153">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="dcb3d-154">A ID do aplicativo para Human Resources é f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-154">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="dcb3d-155">Use esta ID para garantir que você escolheu o aplicativo certo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-155">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="dcb3d-156">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-156">Select **Register**.</span></span>

   <span data-ttu-id="dcb3d-157">[![Registrando um novo aplicativo no portal do Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="dcb3d-157">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="dcb3d-158">O Azure AD atribui uma ID de aplicativo exclusiva (ID de cliente) ao seu aplicativo e o leva à página **Visão geral** do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-158">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="dcb3d-159">Para adicionar mais recursos ao aplicativo, você pode selecionar outras opções de configuração, como opções para identificação de marca, certificados e segredos.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-159">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="dcb3d-160">Como recuperar um token de acesso</span><span class="sxs-lookup"><span data-stu-id="dcb3d-160">Retrieving an access token</span></span>

<span data-ttu-id="dcb3d-161">Os detalhes específicos de como você recupera um token de acesso para chamar a API de dados do Human Resources dependerá de quais tecnologias você está usando para desenvolver o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-161">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="dcb3d-162">Por exemplo, você pode estar [testando com um utilitário de terceiros](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (como o Postman), desenvolvendo um aplicativo de console C# ou serviço Web ou criando um cliente JavaScript/TypeScript.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-162">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="dcb3d-163">Exemplo do aplicativo cliente C#:</span><span class="sxs-lookup"><span data-stu-id="dcb3d-163">Example C# client application:</span></span>
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

<span data-ttu-id="dcb3d-164">Após recuperar um token de acesso, você passará o token no cabeçalho de autorização como um token de portador com cada solicitação enviada para a API de dados, conforme descrito acima.</span><span class="sxs-lookup"><span data-stu-id="dcb3d-164">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
