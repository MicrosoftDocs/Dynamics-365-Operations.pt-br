---
title: Domínios no Dynamics 365 Commerce
description: Este tópico descreve como os domínios são tratados no Microsoft Dynamics 365 Commerce.
author: BrShoo
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: d855f2164e4ee0f0cdb220787eb96217523137e3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010238"
---
# <a name="domains-in-dynamics-365-commerce"></a>Domínios no Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tópico descreve como os domínios são tratados no Microsoft Dynamics 365 Commerce.

Os domínios são endereços da Web usados para navegar até sites do Dynamics 365 Commerce em um navegador da Web. Você controla o gerenciamento do seu domínio com um provedor DNS (Servidor de Nomes de Domínio) escolhido. Os domínios são referenciados no construtor de sites do Dynamics 365 Commerce para coordenar como um site será acessado quando publicado. Este tópico examina como os domínios são tratados e referenciados ao longo do ciclo de vida de desenvolvimento e lançamento de sites do Commerce.

## <a name="provisioning-and-supported-host-names"></a>Provisionamento e nomes de host com suporte

Ao provisionar um ambiente de comércio eletrônico no [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), a caixa **Nomes de host com suporte** na tela de provisionamento de comércio eletrônico é usada para inserir domínios que serão associados ao ambiente implantado do Commerce. Esses domínios serão os nomes DNS (Servidor de Nomes de Domínio) voltados para o cliente em que sites de comércio eletrônico serão hospedados. A inserção de um domínio nessa fase não começa a desviar o tráfego do domínio para o Dynamics 365 Commerce. O tráfego de um domínio só será encaminhado para o ponto de extremidade do Commerce quando o registro CNAME do DNS for atualizado para usar esse ponto de extremidade com o domínio.

> [!NOTE]
> Vários domínios podem ser inseridos na caixa **Nomes de host com suporte** separando-os com ponto-e-vírgula.

A ilustração a seguir mostra a tela de provisionamento de comércio eletrônico do LCS com a caixa **Nomes de host com suporte** realçada. 

![Tela de provisionamento de comércio eletrônico do LCS com a caixa **Nomes de host com suporte** realçada](./media/Domains_ProvisioningeCommerceScreen.png)

Você pode criar uma solicitação de serviço para adicionar outros domínios a um ambiente se o provisionamento já tiver ocorrido. Para criar uma solicitação de serviço no LCS, no seu ambiente, vá para **Suporte \> Problemas de suporte** e selecione **Enviar um incidente**.

## <a name="commerce-generated-urls"></a>URLs geradas pelo Commerce

Ao provisionar um ambiente de comércio eletrônico do Dynamics 365 Commerce, o Commerce gerará uma URL que será o endereço funcional do ambiente. Essa URL é referenciada no link do site de comércio eletrônico mostrado no LCS depois que o ambiente é provisionado. Uma URL gerada pelo Commerce está no formato `https://<e-commerce tenant name>.commerce.dynamics.com`, em que o nome do locatário de comércio eletrônico é o nome inserido no LCS para o ambiente do Commerce.

Você também pode usar nomes de host de sites de produção em um ambiente de área restrita. Essa opção é ideal para copiar um site de um ambiente de área restrita para produção.

## <a name="site-setup"></a>Configuração do site

Após o provisionamento do ambiente de comércio eletrônico, você deve configurar o site no construtor de sites do Commerce para associá-lo à URL funcional.

Ao configurar um site pela primeira vez no construtor de sites, a caixa de diálogo **Configurar seu Site** será exibida.

A ilustração a seguir mostra a caixa de diálogo **Configurar seu Site** de um site denominado "padrão" quando você acessa o site pela primeira vez no construtor de sites.

![Caixa de diálogo **Configurar seu Site**](./media/Domains_SetupyoursiteScreen.png)

A caixa **Selecionar um domínio** permite que você associe um dos nomes de host com suporte fornecidos para o seu site no LCS ao seu site no construtor de sites.

A caixa **Caminho** pode ser deixada em branco ou outra cadeia de caracteres de caminho pode ser adicionada para que seja refletida na URL funcional. Deixar a caixa **Caminho** em branco associa a URL base gerada pelo Commerce ao site que está sendo configurado no construtor de sites. Os caminhos devem ser exclusivos para cada par de site/domínio. No site e no domínio selecionados, somente um site no ambiente pode usar o caminho em branco ou ser associado a uma cadeia de caracteres de caminho exclusiva. Qualquer cadeia de caracteres adicionada ao campo **Caminho** durante a configuração do site se tornará um subcaminho da URL base gerada pelo Commerce que é usada para acessar o site em um navegador da Web.

> [!NOTE]
> O caminho também é conhecido como o **Caminho de correspondência** ao adicionar um canal na seção de configuração **Configurações do Site \> Canais** do construtor de sites.

Por exemplo, se você tiver um site no construtor de sites chamado "fabrikam" em um locatário de comércio eletrônico chamado "xyz" e configurar o site com um caminho em branco, poderá acessar o conteúdo do site publicado em um navegador da Web acessando diretamente a URL base gerada pelo Commerce:

`https://xyz.commerce.dynamics.com`

Como alternativa, se tivesse adicionado um caminho de "fabrikam" durante a configuração do mesmo site, você acessaria o conteúdo do site publicado em um navegador da Web usando a seguinte URL:

`https://xyz.commerce.dynamics.com/fabrikam`

## <a name="pages-and-urls"></a>Páginas e URLs

Depois que o seu site for configurado com um caminho, todas as URLs associadas às páginas no construtor de sites se basearão na URL funcional (a URL gerada pelo Commerce ou a URL gerada pelo Commerce mais o caminho) do site. A criação de uma nova URL no construtor de sites (**URLS /> +Novo**) selecionando uma página da lista na caixa de diálogo **Nova URL** e inserindo o caminho da URL para essa página associará essa URL à página selecionada. Em seguida, o valor do caminho da URL será acrescentado à URL funcional do site para acessar a página e será rotulado como `./<URL path>` na lista de URLs da página **URLs** no construtor de sites.

A ilustração a seguir mostra a caixa de diálogo **Nova URL** no construtor de sites com um exemplo de caminho de URL realçado. 

![Caixa de diálogo **Nova URL** no construtor de sites](./media/Domains_PageSetup2a.png)

A ilustração a seguir mostra a página **URLs** no construtor de sites com um exemplo de URL realçado na lista.

![Executar a opção do fluxo de usuário no fluxo da política](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a>Domínios no construtor de sites

Os valores dos nomes de host com suporte estão disponíveis para serem associados como um domínio durante a configuração de um site. Ao selecionar um valor de nome de host com suporte como o domínio, você verá o domínio escolhido referenciado no construtor de sites. Esse domínio é apenas uma referência no ambiente do Commerce, seu tráfego ao vivo ainda não será encaminhado para o Dynamics 365 Commerce.

Ao trabalhar com sites no construtor de sites, se houver dois sites configurados com dois domínios diferentes, você poderá acrescentar o atributo **?domain=** à sua URL funcional para acessar o conteúdo do site publicado em um navegador.

Por exemplo, o ambiente "xyz" foi provisionado e dois sites foram criados e associados no construtor de sites: um com o domínio `www.fabrikam.com` e outro com o domínio `www.constoso.com`. Cada site foi configurado usando um caminho em branco. Esses dois sites puderam então ser acessados em um navegador da Web da seguinte maneira usando o atributo **?domain=**:
- `https://xyz.commerce.dynamics.com?domain=www.fabrikam.com`
- `https://xyz.commerce.dynamics.com?domain=www.contoso.com`

Quando uma cadeia de caracteres de consulta de domínio não é fornecida em um ambiente com vários domínios fornecidos, o Commerce usa o primeiro domínio fornecido. Por exemplo, se o caminho "fabrikam" foi fornecido primeiro durante a configuração do site, a URL `https://xyz.commerce.dynamics.com` pode ser usada para acessar o conteúdo do site publicado para `www.fabrikam.com`.

## <a name="traffic-forwarding-in-production"></a>Encaminhamento de tráfego na produção

Você pode simular vários domínios usando parâmetros de cadeias de caracteres de consulta de domínio no próprio ponto de extremidade commerce.dynamics.com. No entanto, quando você precisar ficar ativo na produção, deverá encaminhar o tráfego do seu domínio personalizado para o ponto de extremidade `<e-commerce tenant name>.commerce.dynamics.com`.

O ponto de extremidade `<e-commerce tenant name>.commerce.dynamics.com` não oferece suporte a protocolos SSL de domínios personalizados, portanto, você deve configurar esses domínios usando um serviço de front door ou uma CDN (rede de distribuição de conteúdo). 

Para configurar domínios personalizados usando um serviço de front door ou uma CDN, você tem duas opções:

- Configurar um serviço de front door como o Azure Front Door para lidar com tráfego front-end e conectar-se ao seu ambiente do Commerce. Isso oferece maior controle sobre o gerenciamento de domínios e certificados, além de políticas de segurança mais granulares.
- Usar a instância do Azure Front Door fornecida pelo Commerce. Isso requer a coordenação de ações com a equipe do Dynamics 365 Commerce para a verificação de domínio e a obtenção de certificados SSL para o seu domínio de produção.

Para obter informações sobre como configurar um serviço de CDN diretamente, consulte [Adicionar suporte para uma rede de distribuição de conteúdo (CDN)](add-cdn-support.md).

Para usar a instância do Azure Front Door fornecida pelo Commerce, você deve criar uma solicitação de serviço para obter assistência de configuração da CDN da equipe de integração do Commerce. 

- Você precisará fornecer o nome da empresa, o domínio de produção, a ID do ambiente e o nome do locatário de produção de comércio eletrônico. 
- Você precisará confirmar se esse é um domínio existente (usado para um site ativo no momento) ou um novo domínio. 
- Para um novo domínio, a verificação de domínio e o certificado SSL podem ser obtidos em uma única etapa. 
- Para um domínio que atende a um site existente, há um processo de várias etapas necessário para estabelecer a verificação de domínio e o certificado SSL. Esse processo tem um contrato de nível de serviço (SLA) de 7 dias úteis para um domínio entrar no ar, pois ele inclui várias etapas sequenciais.

Para criar uma solicitação de serviço no LCS, no seu ambiente, vá para **Suporte \> Problemas de suporte** e selecione **Enviar um incidente**.

> [!NOTE]
> Os domínios personalizados com SSL só têm suporte em ambientes de produção. Para ambientes que não são de produção, como os de área restrita e de teste de aceitação do usuário (UAT), use a URL gerada pelo Commerce para acessar o conteúdo publicado em um navegador da Web.

## <a name="ssl-certificate-process"></a>Processo de certificado SSL

Quando uma solicitação de serviço for registrada, a equipe do Commerce coordenará as seguintes etapas com você.

Para novos domínios:
- A equipe do Commerce configurará a instância do Azure Front Door (hospedada no Commerce).
- Em seguida, ela fornecerá o registro CNAME para apontar seu domínio personalizado.
- Depois que o registro CNAME for atualizado, a instância do Azure Front Door hospedada no Commerce poderá verificar a propriedade do domínio e obter o certificado SSL.

Para domínios existentes/ativos:
- A equipe do Commerce instruirá você a adicionar um registro CNAME `afdverify.<custom-domain>` para ser fornecido ao provedor DNS do seu domínio.
- Após a conclusão, ela adicionará o domínio à instância do Azure Front Door e fornecerá mais registros TXT de DNS para serem adicionados ao DNS do domínio.
- Depois que os registros TXT forem concluídos, a equipe do Commerce concluirá as atualizações do Azure Front Door para o domínio que configurará o certificado SSL.

## <a name="apex-domains"></a>Domínios apex

A instância do Azure Front Door fornecida pelo Commerce não oferece suporte a domínios apex (domínios raiz que não contêm subdomínios). Os domínios apex exigem um endereço IP para resolução e a instância do Azure Front Door do Commerce existe somente com pontos de extremidade virtuais. Para usar um domínio apex, você tem duas opções:

- **Opção 1** - Usar seu provedor DNS para redirecionar o domínio apex para um domínio "www". Por exemplo, fabrikam.com redireciona para `www.fabrikam.com`, em que `www.fabrikam.com` é o registro CNAME que aponta para a instância do Azure Front Door hospedada no Commerce.

- **Opção 2** - Configurar uma instância de CDN/front door por conta própria para hospedar o domínio apex.

> [!NOTE]
> Se você estiver usando o Azure Front Door, também deverá configurar um DNS do Azure na mesma assinatura. O domínio apex hospedado no DNS do Azure pode apontar para o seu Azure Front Door como um registro de alias. Essa é a única solução, pois os domínios apex sempre devem apontar para um endereço IP.

  ## <a name="additional-resources"></a>Recursos adicionais

  [Implantar um novo locatário de comércio eletrônico](deploy-ecommerce-site.md)

  [Configurar um canal da loja online](online-stores.md)

  [Criar um site de comércio eletrônico](create-ecommerce-site.md)

  [Associar um site do Dynamics 365 Commerce a um canal online](associate-site-online-store.md)

  [Gerenciar arquivos robots.txt](manage-robots-txt-files.md)

  [Carregar redirecionamentos de URL em massa](upload-bulk-redirects.md)

  [Configurar um locatário B2C do Commerce](set-up-B2C-tenant.md)

  [Configurar páginas personalizadas para logons dos usuários](custom-pages-user-logins.md)

  [Configurar múltiplos locatários B2C em um ambiente do Commerce](configure-multi-B2C-tenants.md)

  [Adicionar suporte para uma rede de entrega de conteúdo (CDN)](add-cdn-support.md)

  [Habilitar detecção de lojas com base na localização](enable-store-detection.md)
