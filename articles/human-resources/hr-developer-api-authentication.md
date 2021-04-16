---
title: Autenticação
description: Este artigo fornece informações gerais sobre como autenticar com a interface de programa aplicativo (API) do Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 3dffe1db98ba39fde2229e69bc70bdbf113ff6ad
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793672"
---
# <a name="authentication"></a>Autenticação

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo fornece informações gerais sobre como autenticar com a interface de programa aplicativo (API) do Microsoft Dynamics 365 Human Resources.

## <a name="overview"></a>Visão geral

A API de dados do Human Resources é uma implementação do OData. Para obter mais informações, consulte o [protocolo de dados abertos (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

Seu aplicativo deve ser autenticado como um chamador autorizado antes que a API atenda solicitações de seu aplicativo.

## <a name="fundamentals"></a>Conceitos básicos

Para chamar a API de dados, seu aplicativo deve adquirir um token de acesso da plataforma de identidade da Microsoft. O token de acesso contém informações sobre o seu aplicativo e a permissão que ele tem para chamar recursos no Human Resources.

### <a name="access-token"></a>Token de acesso

Os tokens de acesso emitidos pela plataforma de identidade da Microsoft são tokens da Web JSON (JavaScript Object Notation) codificados em base64 (JWTs). Eles contêm informações (declarações) que a API de dados (e outras APIs da Web que são protegidas pela plataforma de identidade da Microsoft) utiliza para validar o chamador e verificar se o chamador tem as permissões corretas para executar a operação que está solicitando. Durante chamadas, você pode tratar tokens de acesso como opacos. Você deve sempre transmitir tokens de acesso por um canal seguro, como TLS (segurança da camada de transporte) e HTTPS (Hypertext Transfer Protocol Secure).

Este é um exemplo de um token de acesso que é emitido pela plataforma de identidade da Microsoft.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Para chamar a API de dados, anexe o token de acesso como um token de portador ao cabeçalho de autorização na sua solicitação HTTP. Veja aqui um exemplo.

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Registre um novo aplicativo usando o portal do Azure

1. Entre no [portal do Microsoft Azure](https://portal.azure.com) com uma conta de trabalho ou escolar ou uma conta pessoal da Microsoft.

2. Se a sua conta conceder acesso a mais de um locatário, selecione sua conta no canto superior direito e defina a sessão de portal para o locatário do Azure Active Directory (Azure AD) desejado.

3. No painel esquerdo, selecione o serviço **Azure Active Directory** e, em seguida, **Registros de aplicativos \>Novo registro**.

4. Quando a página **Registrar um aplicativo** for exibida, insira as informações de registro do seu aplicativo:

    - **Nome**: Insira um nome de aplicativo significativo que será mostrado aos usuários do aplicativo.
    - **Tipos de conta com suporte**: selecione os tipos de contas aos quais seu aplicativo deve dar suporte.

        | Tipos de conta compatíveis | Descrição |
        |-------------------------|-------------|
        | Contas neste diretório organizacional somente | Selecione esta opção se estiver criando um aplicativo de linha de negócios. Esta opção não está disponível a menos que você esteja registrando o aplicativo em um diretório.<p>Esta opção é mapeada somente para **Azure AD com um único locatário**.</p><p>Esta opção é padrão, a menos que você esteja registrando o aplicativo fora de um diretório. Nesse caso, a opção padrão é **Azure AD multilocatário e contas pessoais da Microsoft**.</p> |
        | Contas em qualquer diretório organizacional | Selecione esta opção para direcionar todos os clientes comerciais e educacionais.<p>Esta opção é mapeada somente para **Azure AD multilocatário**.</p><p>Se você tiver registrado o aplicativo como **Azure AD com um único locatário**, poderá usar o blade **Autenticação** para atualizá-lo com **Azure AD somente multilocatário** e voltar ao **Azure AD com um único locatário**.</p> |
        | Contas em qualquer diretório organizacional e contas pessoais da Microsoft | Selecione esta opção para direcionar o conjunto mais amplo de clientes.<p>Esta opção é mapeada para **Azure AD multilocatário e contas pessoais da Microsoft**.</p><p>Se você tiver registrado o aplicativo como **Azure AD multilocatário e contas pessoais da Microsoft**, não poderá alterar essa configuração na interface do usuário (IU). Em vez disso, você deve usar o editor de manifesto de aplicativo para alterar os tipos de conta com suporte.</p> |

    - **Redirecionar URI (opcional)** – Selecione o tipo de aplicativo que você está criando: **Web** ou **cliente púbico (móvel e desktop)**. Em seguida, insira o URI de redirecionamento (ou URL de resposta) para o aplicativo.

        - Para aplicativos Web, forneça a URL base do aplicativo. Por exemplo, `http://localhost:31544` pode ser a URL de um aplicativo Web executado no seu computador local. Os usuários utilizam esta URL para entrar em um aplicativo cliente Web.
        - Para aplicativos de cliente público, forneça o URI que o Azure AD usa para retornar respostas de token. Insira um valor específico para seu aplicativo, como `myapp://auth`.

        Para ver exemplos específicos para aplicativos Web ou aplicativos nativos, consulte o início rápido na [plataforma de identidades da Microsoft (antes Azure Active Directory para desenvolvedores)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).

5. Em **Permissões de API**, selecione **Adicionar uma permissão**. Em seguida, na guia **APIs que minha organização utiliza**, procure o **Dynamics 365 Human Resources** e adicione a permissão **user\_impersonation** ao seu aplicativo. A ID do aplicativo para Human Resources é f9be0c49-aa22-4ec6-911a-c5da515226ff. Use esta ID para garantir que você escolheu o aplicativo certo.

6. Selecione **Registrar**.

   [![Registrando um novo aplicativo no portal do Azure](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

O Azure AD atribui uma ID de aplicativo exclusiva (ID de cliente) ao seu aplicativo e o leva à página **Visão geral** do seu aplicativo. Para adicionar mais recursos ao aplicativo, você pode selecionar outras opções de configuração, como opções para identificação de marca, certificados e segredos.

## <a name="retrieving-an-access-token"></a>Como recuperar um token de acesso

Os detalhes específicos de como você recupera um token de acesso para chamar a API de dados do Human Resources dependerá de quais tecnologias você está usando para desenvolver o aplicativo cliente. Por exemplo, você pode estar [testando com um utilitário de terceiros](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (como o Postman), desenvolvendo um aplicativo de console C# ou serviço Web ou criando um cliente JavaScript/TypeScript.

Exemplo do aplicativo cliente C#:
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

Após recuperar um token de acesso, você passará o token no cabeçalho de autorização como um token de portador com cada solicitação enviada para a API de dados, conforme descrito acima.


[!INCLUDE[footer-include](../includes/footer-banner.md)]