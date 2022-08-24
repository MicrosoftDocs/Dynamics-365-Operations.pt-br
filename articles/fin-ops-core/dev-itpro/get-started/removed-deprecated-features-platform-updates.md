---
title: Recursos de Platform removidos ou preteridos
description: Este artigo descreve os recursos que foram removidos ou planejados para remoção em atualizações de plataforma de aplicativos de finanças e operações.
author: sericks007
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b2eec4dd71baef54877b4139a331288bf37f4960
ms.sourcegitcommit: e4b6521337dfff3515f70086b0125d4c23308c71
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9262288"
---
# <a name="removed-or-deprecated-platform-features"></a>Recursos de Platform removidos ou preteridos

[!include [banner](../includes/banner.md)]

Este artigo descreve os recursos que foram removidos ou planejados para remoção em atualizações de plataforma de aplicativos de finanças e operações.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

Informações detalhadas sobre objetos em aplicativos de finanças e operações podem ser encontradas nos [Relatórios de referência técnica](/dynamics/s-e/global/axtechrefrep_61). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão de aplicativos de finanças e operações.

## <a name="feature-deprecation-effective-august-2022"></a>Substituição de recurso efetiva em agosto de 2022

### <a name="lifecycle-services-lcs-features-deprecated-in-august-2022"></a>Recursos preteridos do Lifecycle Services (LCS) em agosto de 2022

Como parte do esforço de trabalho da [Plataforma Um do One Dynamics](/dynamics365-release-plan/2022wave2/finance-operations/finance-operations-crossapp-capabilities/one-dynamics-one-platform), os seguintes recursos do LCS foram preteridos.

| Nome do recurso | Usado com AX 2012? | Usado com os aplicativos de finanças e operações? | Substituída por outro recurso? |
|--------------|--------------------|----------------------------------------|------------------------------|
| Anúncios | Sim | Sim | Sim: as faixas existem em páginas de projeto e de ambiente individuais para notificações. |
| Gerenciador de configurações | Sim | Número | Número |
| Análise de travamento e despejo | Sim | Número | Número |
| Comentários e bugs | Sim | Sim | Número |
| Minha assinatura | Sim | Sim | Número |
| Office 365 | Sim | Sim | Sim: portal de administração do Azure Active Directory ou da Microsoft. |
| Análise de impacto | Número | Sim | Número |
| Estimador de impacto econômico total | Número | Sim | Número |
| Solicitações de serviço | Número | Sim | Sim: [Implantações de autoatendimento](../deployment/infrastructure-stack.md) |
| Integração do SharePoint | Sim | Sim | Número |
| Gerenciador de configurações e dados | Número | Sim | Número |
| Pacotes de dados do processo | Número | Sim | Sim: Estrutura de Importação/Exportação de Dados (DIXF) |
| Atualização do ambiente | Número | Sim | Sim: as atualizações do serviço [One Version](../lifecycle-services/oneversion-overview.md) estão disponíveis. |
| Avaliador de infraestrutura | Sim | Número | Número |
| Dimensionamento da licença | Sim | Número | Número |
| Criador de perfil de uso | Sim | Número | Número |
| Análise de personalizações | Sim | Número | Número |
| Diagnóstico do sistema | Sim | Sim | Número |
| Gerenciamento Vision do modelador de processo de negócios | Sim | Sim | Número |
| Gerenciamento do ambiente de nuvem do AX 2012 | Sim | Número | Número |
| Conectores do Azure RDFE | Sim | Sim | Número |
| Versões do AX 2012 | Sim | Número | Número |
| Itens de trabalho armazenados no armazenamento LCS | Sim | Sim | Número |
| Solicitações de hotfix | Sim | Sim | Número |


### <a name="transport-layer-security-tls-rsa-cipher-suites"></a>Suítes de criptografia de RSA de TLS (Transport Layer Security)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos removendo a lista de pacotes de criptografia a seguir para cumprir os protocolos de segurança atuais.<br><br>TLS_RSA_WITH_AES_256_GCM_SHA384<br>TLS_RSA_WITH_AES_128_GCM_SHA256<br>TLS_RSA_WITH_AES_256_CBC_SHA256<br>TLS_RSA_WITH_AES_128_CBC_SHA256<br>TLS_RSA_WITH_AES_256_CBC_SHA<br>TLS_RSA_WITH_AES_256_CBC_SHA  |
| **Substituída por outro recurso?**   | A partir de 30 de novembro de 2022, os clientes só podem usar [conjuntos de criptografia padrão](/power-platform/admin/server-cipher-tls-requirements). Essa alteração afeta os clientes e os servidores que se comunicam com os nossos servidores, por exemplo, podem impactar as integrações de terceiros que não estão seguindo os pacotes de criptografia padrão. |
| **Áreas afetadas do produto**         | Aplicativos do Finance and Operations |
| **Opção de implantação**              | Implantações na nuvem |
| **Status**                         | Preterido. Os clientes devem atualizar seus servidores antes de 30 de novembro de 2022. Para obter mais informações sobre como configurar a ordem do Conjunto de Criptografia de TLS, consulte [Gerenciar TLS (Transport Layer Security)](/windows-server/security/tls/manage-tls).  |


## <a name="feature-deprecation-effective-june-2022"></a>Substituição de recurso efetiva em junho de 2022

### <a name="finance-and-operations-dynamics-365-mobile-application-and-mobile-platform"></a>Aplicativo e plataforma móveis de finanças e operações (Dynamics 365) 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos substituindo o aplicativo e a plataforma móveis de finanças e operações (Dynamics 365) para consolidar em uma única plataforma móvel, que é o Power Apps. |
| **Substituída por outro recurso?**   | Sim, as experiências para dispositivos móveis sobre os dados do aplicativo de finanças e operações podem ser criadas com a integração do Power Platform. Consulte a [postagem no blog](https://cloudblogs.microsoft.com/dynamics365/it/2022/06/03/finance-and-operations-dynamics-365-mobile-app-to-be-deprecated/) e [Criando experiências móveis](../power-platform/build-mobile-experiences.md) para obter mais detalhes. |
| **Áreas afetadas do produto**         | Aplicativos do Finance and Operations |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido. A data de término do suporte está prevista para outubro de 2024. |


## <a name="platform-updates-for-version-10029-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.29 de aplicativos de finanças e operações

### <a name="panorama-tab-style"></a>Estilo da guia Panorama

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As páginas de rolagem horizontal se alinham a padrões de layout desatualizados que têm problemas conhecidos de usabilidade e acessibilidade.  |
| **Substituída por outro recurso?**   | Não, mas outros estilos de guia ainda estão disponíveis. |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido. |


## <a name="feature-deprecation-effective-april-2022"></a>Substituição de recurso efetiva em abril de 2022

### <a name="xml-url-resolution-in-data-management"></a>Resolução de URL XML no Gerenciamento de dados 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos removendo o suporte à resolução de URL XML, pois ele foi identificado como uma vulnerabilidade de segurança potencial. Isso significa que os recursos externos associados a arquivos XML não serão mais resolvidos.  |
| **Substituída por outro recurso?**   | Não. |
| **Áreas afetadas do produto**         | Aplicativos do Finance and Operations |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido. |

## <a name="feature-deprecation-effective-march-14-2022"></a>Substituição de recurso efetiva em 14 de março de 2022

### <a name="xslt-scripting-in-data-management"></a>Scripts XSLT no gerenciamento de dados

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O suporte ao script XSLT no Gerenciamento de dados foi preterido para melhorar a segurança e a proteção de dados nos aplicativos de finanças e operações.  |
| **Substituída por outro recurso?**   | Não. Os clientes e os ISVs devem considerar a reimplementação de suas soluções com base no idioma X++, no lugar do script XSLT. |
| **Áreas afetadas do produto**         | Aplicativos do Finance and Operations |
| **Opção de implantação**              | Todos |
| **Status**                         | Preterido <br><br>**Exceção**: clientes que estão usando scripts XLST no momento. Eles podem continuar a usá-los até que eles sejam atualizados para a versão 10.0.30 ou posterior. Para versões anteriores, a exceção vai expirar em 31 de janeiro de 2023. Os clientes com essa exceção receberam uma notificação no Centro de mensagens disponível no Centro de administração do Microsoft 365. |

## <a name="feature-removal-effective-october-2021"></a>Remoção de recursos em outubro de 2021

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Relatórios SQL do Microsoft Azure no LCS (Lifecycle Services)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Todas as atividades e o monitoramento serão executados internamente pela plataforma, por meio da automação. Isso não exigirá intervenção manual.|
| **Substituída por outro recurso?**   | Sim, agora existe um sistema automatizado, o que torna esses recursos obsoletos. |
| **Áreas afetadas do produto**         | Relatórios SQL: DTU Atual, Detalhes de DTU Atuais, Obter Detalhes de Bloqueio, Lista de Guias de Plano Atual, Obter Lista de IDs de Consulta, Obter plano de consulta SQL para uma ID de plano específica, Obter planos de consulta e status de execução, Obter configuração de restrição, Obter estatísticas de espera, Listar consultas mais caras |
| **Opção de implantação**              | Implantação na nuvem: afeta os ambientes de produção gerenciados pela Microsoft e os ambientes de área restrita da Camada 2 até a Camada 5. |
| **Status**                         | Removido |

### <a name="azure-sql-actions-in-lcs"></a>Ações do SQL do Azure no LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos substituindo algumas ações SQL no LCS. Todas as atividades e o monitoramento serão executados internamente pela plataforma, por meio da automação. Isso não exigirá intervenção manual. |
| **Substituída por outro recurso?**   | Sim, agora existe um sistema automatizado, o que torna esses recursos obsoletos. |
| **Áreas afetadas do produto**         | Ações SQL: Criar um guia de plano para impor a ID do Plano, Criar um guia de plano para adicionar dicas de tabela, Remover guia de Plano, Desabilitar/Habilitar bloqueios de página e escalonamento de bloqueio, Atualizar estatísticas em uma tabela, Recriar Índice, Criar Índice |
| **Opção de implantação**              | Implantação na nuvem: afeta os ambientes de produção gerenciados pela Microsoft e os ambientes de área restrita da Camada 2 até a Camada 5. |
| **Status**                         | Removido |


## <a name="feature-deprecation-effective-october-2021"></a>Substituição de recursos em outubro de 2021

### <a name="show-related-document-attachments-feature"></a>Recurso "Mostrar anexos de documentos relacionados"

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O recurso estava retornando resultados inesperados. |
| **Substituída por outro recurso?**   | Não. Os planos adicionais referentes a essa funcionalidade serão comunicados por meio do nosso processo padrão de divulgação de ciclos de lançamentos. |
| **Áreas afetadas do produto**         | Cliente Web - Experiência de anexo de documento |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.23 de aplicativos de finanças e operações

### <a name="ondbsynchronize-event"></a>Evento OnDBSynchronize

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não há um controle para executar esse evento. |
| **Substituída por outro recurso?**   | Sim, mover métodos existentes inscritos pelo evento **OnDBSynchronize** para uma classe estendida SysSetup. |
| **Áreas afetadas do produto**         | Sincronização de banco de dados |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido. A data de remoção planejada é outubro de 2022. |


### <a name="systemnotificationsmanageraddnotification-api"></a>API SystemNotificationsManager.AddNotification

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A Microsoft requer mais parâmetros ao adicionar notificações. |
| **Substituída por outro recurso?**   | Sim, a API **SystemNotificationsManager.AddSystemNotification()**. Essa API requer a definição explícita de ExpirationDateTime e RuleID para notificações geradas. |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido. A data de remoção planejada é abril de 2023. |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.21 de aplicativos de finanças e operações

### <a name="skype-for-business-online-support"></a>Suporte do Skype for Business Online

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O Skype for Business Online foi desativado. Para obter mais informações, consulte [O serviço Skype for Business Online foi desativado](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601). |
| **Substituída por outro recurso?**   | Atualmente não, embora possamos considerar adicionar a presença do Teams no futuro.|
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Tudo |
| **Status**                         | Preterido. A configuração **Skype habilitado** foi desativada a partir da versão 10.0.21. A remoção dessa configuração está prevista para abril de 2022; no entanto, o recurso deixará de funcionar depois que a equipe do Skype encerrar o serviço. |
 
## <a name="feature-deprecation-effective-august-2021"></a>Substituição de recurso efetiva em agosto de 2021

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Relatórios SQL do Microsoft Azure no LCS (Lifecycle Services)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Todas as atividades e o monitoramento serão executados internamente pela plataforma, por meio da automação. Isso não exigirá intervenção manual.|
| **Substituída por outro recurso?**   | Sim, agora existe um sistema automatizado, o que torna esses recursos obsoletos. |
| **Áreas afetadas do produto**         | Relatórios SQL: DTU Atual, Detalhes de DTU Atuais, Obter Detalhes de Bloqueio, Lista de Guias de Plano Atual, Obter Lista de IDs de Consulta, Obter plano de consulta SQL para uma ID de plano específica, Obter planos de consulta e status de execução, Obter configuração de restrição, Obter estatísticas de espera, Listar consultas mais caras |
| **Opção de implantação**              | Implantação na nuvem: afeta os ambientes de produção gerenciados pela Microsoft e os ambientes de área restrita da Camada 2 até a Camada 5. |
| **Status**                         | Preterido: a data de remoção planejada é outubro de 2021. |

### <a name="azure-sql-actions-in-lcs"></a>Ações do SQL do Azure no LCS

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos substituindo algumas ações SQL no LCS. Todas as atividades e o monitoramento serão executados internamente pela plataforma, por meio da automação. Isso não exigirá intervenção manual. |
| **Substituída por outro recurso?**   | Sim, agora existe um sistema automatizado, o que torna esses recursos obsoletos. |
| **Áreas afetadas do produto**         | Ações SQL: Criar um guia de plano para impor a ID do Plano, Criar um guia de plano para adicionar dicas de tabela, Remover guia de Plano, Desabilitar/Habilitar bloqueios de página e escalonamento de bloqueio, Atualizar estatísticas em uma tabela, Recriar Índice, Criar Índice |
| **Opção de implantação**              | Implantação na nuvem: afeta os ambientes de produção gerenciados pela Microsoft e os ambientes de área restrita da Camada 2 até a Camada 5. |
| **Status**                         | Preterido: a data de remoção planejada é outubro de 2021. |

## <a name="feature-deprecation-effective-may-2021"></a>Substituição de recurso efetiva em maio de 2021

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Portal de globalização no Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Estamos descontinuando o portal de globalização no LCS, pois esse recurso foi substituído por outros serviços baseados no LCS. |
| **Substituída por outro recurso?**   | Sim, este recurso foi substituído por [Pesquisa de problemas](../lifecycle-services/issue-search-lcs.md) e [Serviço de envio de alertas regulatórios do Dynamics](../lcs-solutions/submit-localization-alerts.md). |
| **Áreas afetadas do produto**         | Portal de globalização no LCS|
| **Opção de implantação**              | Implantação de nuvem |
| **Status**                         | Preterido: a data de remoção planejada é maio de 2022. |


## <a name="feature-removed-effective-january-28-2021"></a>Recurso removido em 28 de janeiro de 2021

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Trabalhos em lotes para tratar da desfragmentação de índice SQL

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para reduzir a sobrecarga de operação, monitoramento e manutenção do gerenciamento de índices pelos clientes, este recurso foi removido. |
| **Substituída por outro recurso?**   | A partir de agora, a manutenção do índice será realizada pelos serviços da Microsoft. Isso ocorrerá continuamente sem afetar as cargas de trabalho do usuário. |
| **Áreas afetadas do produto**         | Aplicativos do Finance and Operations|
| **Opção de implantação**              | Implantação na nuvem - afeta os ambientes de produção gerenciados pela Microsoft e os ambientes de área restrita da Camada 2 até a Camada 5. |
| **Status**                         | Este recurso foi removido. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.17 de aplicativos de finanças e operações


### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para dar suporte às versões mais recentes do Visual Studio, algumas alterações devem ser feitas nas extensões X++ para Visual Studio. Essas alterações são incompatíveis com o Visual Studio 2015. |
| **Substituída por outro recurso?**   | O Visual Studio 2017 substituirá o Visual Studio 2015 como a versão implantada e necessária. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: após a atualização, as ferramentas X++ anteriores serão removidas do Visual Studio 2015, e as ferramentas atualizadas não serão instaladas no Visual Studio 2015. Não haverá impacto nos builds hospedados. Para máquinas virtuais de build, o pipeline de build (definição de build) precisa ser atualizado manualmente para alterar a dependência do MSBuild 14.0 (Visual Studio 2015) ao MSBuild 15.0 (Visual Studio 2017) conforme descrito em [Atualizar um pipeline herdado no Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Avatar do usuário 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O avatar do usuário exibido no lado direito da barra de navegação foi recuperado usando uma API do controle de cabeçalho do Dynamics 365, que foi preterido. |
| **Substituída por outro recurso?**   | Em vez disso, os usuários verão suas iniciais em um círculo na barra de navegação. Esse é o mesmo visual usado atualmente em máquinas de desenvolvimento. |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Removido a partir da versão 10.0.17 |

### <a name="enterprise-portal-ep-deprecation"></a>Reprovação do Enterprise Portal (EP)  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os artefatos de metadados associados ao Dynamics AX 2012 Enterprise Portal (EP) foram preteridos, pois o EP nunca teve suporte nos aplicativos de finanças e operações. |
| **Substituída por outro recurso?**   | Número |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: todo o código do EP está programado para ser removido na versão de outubro de 2021. |

## <a name="deprecation-effective-december-2020"></a>Substituição efetiva em dezembro de 2020

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Suporte do Internet Explorer 11 para Dynamics 365 foi substituído

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Desde dezembro de 2020, foi preterido o suporte do Microsoft Internet Explorer 11 para todos os produtos do Dynamics 365 e o Dynamics Lifecycle Services (LCS). O Internet Explorer 11 não tem mais suporte desde agosto de 2021.<br><br>Isso afetará os clientes que usam produtos do Dynamics 365 e o LCS projetados para serem usados por meio de uma interface do Internet Explorer 11. Depois de agosto de 2021, o Internet Explorer 11 não tem suporte para esses produtos do Dynamics 365 e o LCS. |
| **Substituída por outro recurso?**   | Recomendamos que os clientes façam a transição para o Microsoft Edge.|
| **Áreas afetadas do produto**         | Todos os produtos do Dynamics 365 e o LCS |
| **Opção de implantação**              | Todos|
| **Status**                         | Preterido: Internet Explorer 11 não terá suporte depois de agosto de 2021.|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.15 de aplicativos de finanças e operações

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Suplemento do Visual Studio para aplicar hotfixes de metadados

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Não há mais suporte para hotfixes de metadados com as atualizações de serviço do [One Version](../../fin-ops/get-started/one-version.md) introduzidas em julho de 2018 com a versão 8.1. |
| **Substituída por outro recurso?**   | Hotfixes de metadados individuais não estão disponíveis para versões com suporte. As atualizações de qualidade cumulativas serão aplicadas. |
| **Áreas afetadas do produto**         | Suplementos do Visual Studio |
| **Opção de implantação**              | Máquinas virtuais de desenvolvimento |
| **Status**                         | Com a versão 10.0.15, o suplemento não é mais incluído nas ferramentas do Visual Studio. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.14 de aplicativos de finanças e operações

### <a name="online-users-page"></a>Página de usuários online 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Esta é uma página herdada criada para a arquitetura anterior de cliente/servidor. As informações nesta página nem sempre são precisas, podem ser confusas e enganosas. |
| **Substituída por outro recurso?**   | Forneceremos uma nova página em uma atualização futura.|
| **Áreas afetadas do produto**         | Administração do Sistema |
| **Opção de implantação**              | Todas |
| **Status**                         | Em outubro de 2021 este formulário será removido.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.13 de aplicativos de finanças e operações


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Código personalizado definido nas propriedades do relatório SSRS 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Em geral, o código personalizado oferece benefícios limitados enquanto que, ao mesmo tempo, requer recursos e uma computação significativos para o suporte. O código personalizado é usado principalmente pelos autores de relatórios para chamar métodos públicos a partir de um assembly de código personalizado. No entanto, o serviço hospedado na nuvem não oferece suporte a referências a assemblies personalizados para relatórios SSRS. |
| **Substituída por outro recurso?**   | Autores de relatórios podem optar por continuar fazendo referência a APIs públicas do .NET para operações matemáticas, de conversão e de formatação de qualquer expressão de caixa de texto. Para obter mais informações, consulte [Adicionar código a um relatório (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs).  |
| **Áreas afetadas do produto**         | Subconjunto de designs de relatórios de aplicativos definidos no RDL que contêm código personalizado. |
| **Opção de implantação**              | Todas |
| **Status**                         | Com a versão 10.0.13, o compilador começará a emitir um aviso para instâncias em que o código personalizado for detectado em uma definição de relatório SSRS. Para corrigir o problema, abra a definição do design do relatório e remova todos os artefatos de código personalizado. Este aviso será substituído por um erro do compilador em uma atualização futura.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Atualização de três bibliotecas de componentes jQuery 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Três bibliotecas de componentes jQuery estão sendo atualizadas para correções de segurança e para manter a moeda.   
| **Substituída por outro recurso?**   | As seguintes bibliotecas estão sendo afetadas: jQuery (para a versão 3.5.0 da versão 2.1.4), IU do jQuery (para a versão 1.12.1 da versão 1.11.4), jQuery qTip (para versão 3.0.3 da 2.2.1). As diretrizes de migração foram fornecidas online pelo jQuery.  |
| **Áreas afetadas do produto**         | Controles extensíveis, especificamente códigos JavaScript personalizados usando APIs preteridas ou removidas |
| **Opção de implantação**              | Todas |
| **Status**                         | Com a versão 10.0.13/Platform update 37, os clientes podem, opcionalmente, mudar para as bibliotecas mais recentes habilitando o recurso "Atualizar três bibliotecas de componentes jQuery". A mudança para as novas bibliotecas será obrigatória na versão de abril de 2021 para permitir o tempo de migração de APIs afetadas.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Controle de grade existente/API forceLegacyGrid()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O controle de grade existente está sendo substituído pelo novo controle de grade. |
| **Substituída por outro recurso?**   | O [novo controle de grade](../..//fin-ops/get-started/grid-capabilities.md) |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Na versão 10.0.13, o novo controle de grade está geralmente disponível e os clientes podem ativar esse recurso opcionalmente. O novo controle de grade se tornará ativado, por padrão, com a versão de outubro de 2021. No momento, a intenção é que ele seja obrigatório em abril de 2022. Quando o novo controle de grade se tornar obrigatório, a API **forceLegacyGrid()** não será mais respeitada. |

### <a name="personalization-without-saved-views"></a>Personalização sem exibições salvas 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O subsistema de personalização foi revisado com o recurso de exibições salvas para oferecer um melhor desempenho e recursos adicionais. |
| **Substituída por outro recurso?**   | Exibições salvas |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Na versão 10.0.13/Platform update 37, o recurso de exibições salvas está geralmente disponível e os clientes podem ativar esse recurso opcionalmente. O recurso de exibições salvas se tornará obrigatório na versão de outubro de 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.12 de aplicativos de finanças e operações

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Extensões do formulário de controle de grade ou grupo contendo referências de campo inválidas

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A propriedade de grupo de dados nos controles de grade ou grupo é usada para mostrar automaticamente todos os campos de um grupo de campos. Um controle de grade ou grupo adicionado por extensão pode conter campos que não estejam mais definidos no grupo de campos ou que talvez não tenham campos definidos no grupo de campos. Isso pode causar inconsistência no comportamento em tempo de execução. As atualizações de plataforma para a versão 10.0.12 dos aplicativos de finanças e operações categorizam esse problema como um *aviso* do compilador. Para corrigir esse problema, abra a extensão do formulário e salve-a.
| **Substituída por outro recurso?**   | Este aviso do compilador será substituído por um erro do compilador em uma atualização futura. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Um aviso do compilador foi apresentado em atualizações de plataforma para a versão 10.0.12 dos aplicativos de finanças e operações. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.11 de aplicativos de finanças e operações

### <a name="explicit-safe-lists-for-self-service-environments"></a>Listas de confiança explícitas para ambientes de autoatendimento

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O processo de movimentação de IP para listas de confiança foi alterado. O autoatendimento não oferece mais suporte a listas de confiança de IP. |
| **Substituída por outro recurso?**   | Para obter mais informações, consulte [Configuração do acesso condicional ao Azure Active Directory](/appcenter/general/configuring-aad-conditional-access).|
| **Áreas afetadas do produto**         | Segurança |
| **Opção de implantação**              | Nuvem |
| **Status**                         | Preterido: esse recurso foi totalmente substituído por implantações de autoatendimento. |

### <a name="visual-studio-2015"></a>Visual Studio2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para dar suporte às versões mais recentes do Visual Studio, algumas alterações devem ser feitas nas extensões X++ para Visual Studio. Essas alterações são incompatíveis com o Visual Studio 2015. |
| **Substituída por outro recurso?**   | O Visual Studio 2017 substituirá o Visual Studio 2015 como a versão implantada e necessária. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | As máquinas virtuais implantadas na versão 10.0.13 (Atualização de plataforma 37) ou posteriores contêm o Visual Studio 2017. A versão 10.0.16 (Atualização de plataforma 40) é a versão final com suporte para o Visual Studio 2015. As máquinas virtuais apenas com o Visual Studio 2015 não poderão ser atualizadas para a versão 10.0.17 (Atualização de plataforma 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos contendo referências de campo inválidas

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os grupos de campos nas definições de metadados da tabela podem conter referências de campo inválidas. Se esses grupos de campos forem implantados, eles pode causar falhas de tempo de execução no Financial Reporting e no Microsoft SQL Server Reporting Services (SSRS). A platform update 23 apresentou um *aviso* do compilador que permitiu que esse problema de metadados fosse solucionado. As atualizações de plataforma para a versão 10.0.11 dos aplicativos de finanças e operações categorizam esse problema como um *erro* do compilador.<p>Para corrigir esse problema, siga estas etapas.</p><ol><li>Remova a referência de campo inválida da definição do grupo de campos da tabela.</li><li>Recompilar.</li><li>Certifique-se de que os erros sejam solucionados.</li></ol> |
| **Substituída por outro recurso?**   | Este erro do compilador substitui permanentemente o aviso do compilador.  |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido: o aviso do compilador é um erro do compilador em atualizações de plataforma para a versão 10.0.11 de aplicativos de finanças e operações. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licenças ISV criadas usando o algoritmo de hash SHA1

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O processo para criar licenças de fornecedor independente de software (ISV) foi alterado. Para obter mais informações, consulte o [Licenciamento de fornecedor independente de software (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Substituída por outro recurso?**   | Sim. Use o Windows PowerShell para criar licenças. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Preterido : Licenças ISV criadas usando o algoritmo de hash SHA1. Esse algoritmo dependia de certificados que eram criados usando o utilitário MakeCert, e esse utilitário foi preterido.<br><br>Preterido : O uso de SHA1 para fins de segurança ou hash. O funcionamento do SHA1 será descontinuado no início de 2021. Portanto, não deve mais ser usado.<br><br>Removido: Suporte para solicitações de entrada ou saída do Transport Layer Security (TLS) 1.0 e TLS 1.1. |

## <a name="platform-update-32"></a>Platform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Caixa de diálogo Alterar solicitação de fluxo de trabalho não inclui mais a seleção do usuário de lista suspensa

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Isso foi um problema de segurança, pois a solicitação de alteração poderia ser enviada para um usuário indesejado. Isso também era um problema de usabilidade porque forçava o usuário a determinar quem foi o originador do fluxo de trabalho e selecioná-los manualmente.  |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Fluxo de Trabalho |
| **Opção de implantação**              | Todas |
| **Status**                         | A lista suspensa de seleção de usuário foi removida da caixa de diálogo alteração de solicitação na platform update 23. Solicitações de alteração de solicitação serão enviadas automaticamente para o originador conforme pretendido. Para obter mais informações sobre essa funcionalidade, consulte [Ações em processos de aprovação de fluxo de trabalho](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Links de detalhamento incorporados não são mais compatíveis em documentos paginados renderizados pelo serviço armazenado em nuvem 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As URLs de navegação inseridas nos documentos processados pelo serviço podem conter dados comerciais confidenciais. Estamos removendo o suporte para links de detalhamento incorporados em documentos como uma precaução de segurança para proteger ainda mais os dados dos clientes. Os usuários também se beneficiarão do melhor desempenho enquanto produzem documentos interativamente como resultado dessa alteração.  |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Relatório |
| **Opção de implantação**              | Todas |
| **Status**                         | Este recurso está sendo removido ativamente do serviço.<br><br>O cliente moderno oferece várias opções para produzir exibições que incluem links gerados automaticamente para ajudar na navegação do aplicativo. Os documentos paginados processados pelo serviço são recomendados para comunicações externas enviadas por email, arquivadas e impressas para os destinatários. Aperfeiçoamos a experiência de visualização de documentos diretamente no navegador, que oferece acesso direto a impressoras locais. Para obter mais informações, consulte [Visualização de documentos em PDF com um visualizador incorporado](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

