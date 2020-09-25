---
title: Recursos de plataforma removidos ou obsoletos
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção nas atualizações de plataforma do Finance and Operations apps.
author: sericks007
manager: AnnBe
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: b2d54cfaddc1697eda543952831e745182df2753
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803130"
---
# <a name="removed-or-deprecated-platform-features"></a>Recursos de plataforma removidos ou obsoletos

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção nas atualizações de plataforma do Finance and Operations apps.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.13 dos aplicativos do Finance and Operations


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Código personalizado definido nas propriedades do relatório SSRS 

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Em geral, o código personalizado oferece benefícios limitados enquanto que, ao mesmo tempo, requer recursos e uma computação significativos para o suporte. O código personalizado é usado principalmente pelos autores de relatórios para chamar métodos públicos a partir de um assembly de código personalizado. No entanto, o serviço hospedado na nuvem não oferece suporte a referências a assemblies personalizados para relatórios SSRS. |
| **Substituída por outro recurso?**   | Autores de relatórios podem optar por continuar fazendo referência a APIs públicas do .NET para operações matemáticas, de conversão e de formatação de qualquer expressão de caixa de texto. Para obter mais informações, consulte [Adicionar código a um relatório (SSRS)](https://docs.microsoft.comsql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Áreas afetadas do produto**         | Subconjunto de designs de relatórios de aplicativos definidos no RDL que contêm código personalizado. |
| **Opção de implantação**              | Todas |
| **Status**                         | Com a versão 10.0.13, o compilador começará a emitir um aviso para instâncias em que o código personalizado for detectado em uma definição de relatório SSRS. Para corrigir o problema, abra a definição do design do relatório e remova todos os artefatos de código personalizado. Este aviso será substituído por um erro do compilador em uma atualização futura.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Atualização de três bibliotecas de componentes jQuery 

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Três bibliotecas de componentes jQuery estão sendo atualizadas para correções de segurança e para manter a moeda.   
| **Substituída por outro recurso?**   | As seguintes bibliotecas estão sendo afetadas: jQuery (para a versão 3.5.0 da versão 2.1.4), IU do jQuery (para a versão 1.12.1 da versão 1.11.4), jQuery qTip (para versão 3.0.3 da 2.2.1). As diretrizes de migração foram fornecidas online pelo jQuery.  |
| **Áreas afetadas do produto**         | Controles extensíveis, especificamente códigos JavaScript personalizados usando APIs preteridas ou removidas |
| **Opção de implantação**              | Todas |
| **Status**                         | Com a versão 10.0.13/Atualizaçãod e plataforma 37, os clientes podem, opcionalmente, mudar para as bibliotecas mais recentes habilitando o recurso "Atualizar três bibliotecas de componentes jQuery". A mudança para as novas bibliotecas será obrigatória na versão de abril de 2021 para permitir o tempo de migração de APIs afetadas.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Controle de grade existente/API forceLegacyGrid()

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O controle de grade existente está sendo substituído pelo novo controle de grade. |
| **Substituída por outro recurso?**   | O [novo controle de grade](../..//fin-ops/get-started/grid-capabilities.md) |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Na versão 10.0.13, o novo controle de grade está geralmente disponível e os clientes podem ativar esse recurso opcionalmente. O novo controle de grade se tornará obrigatório na versão de outubro de 2021. Quando o novo controle de grade se tornar obrigatório, a API **forceLegacyGrid()** não será mais respeitada. |

### <a name="personalization-without-saved-views"></a>Personalização sem exibições salvas 

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O subsistema de personalização foi revisado com o recurso de exibições salvas para oferecer um melhor desempenho e recursos adicionais. |
| **Substituída por outro recurso?**   | Exibições salvas |
| **Áreas afetadas do produto**         | Cliente web |
| **Opção de implantação**              | Todas |
| **Status**                         | Na versão 10.0.13/atualização de Plataforma 37, o recurso de exibições salvas está geralmente disponível e os clientes podem ativar esse recurso opcionalmente. O recurso de exibições salvas se tornará obrigatório na versão de outubro de 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.12 dos aplicativos do Finance and Operations

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Extensões do formulário de controle de grade ou grupo contendo referências de campo inválidas

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | A propriedade de grupo de dados nos controles de grade ou grupo é usada para mostrar automaticamente todos os campos de um grupo de campos. Um controle de grade ou grupo adicionado por extensão pode conter campos que não estejam mais definidos no grupo de campos ou que talvez não tenham campos definidos no grupo de campos. Isso pode causar inconsistência no comportamento em tempo de execução. Agora, as atualizações de plataforma para a versão 10.0.12 dos aplicativos do Finance and Operations categorizam esse problema como um *aviso* do compilador. Para corrigir esse problema, abra a extensão do formulário e salve-a.
| **Substituída por outro recurso?**   | Este aviso do compilador será substituído por um erro do compilador em uma atualização futura. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Um aviso do compilador foi introduzido em atualizações de plataforma para a versão 10.0.12 dos aplicativos do Finance and Operations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations

### <a name="explicit-safe-lists-for-self-service-environments"></a>Listas de confiança explícitas para ambientes de autoatendimento

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O processo de movimentação de IP para listas de confiança foi alterado. O autoatendimento não oferece mais suporte a listas de confiança de IP. |
| **Substituída por outro recurso?**   | Para obter mais informações, consulte [Configuração do acesso condicional ao Azure Active Directory](https://docs.microsoft.com/appcenter/general/configuring-aad-conditional-access).|
| **Áreas afetadas do produto**         | Segurança |
| **Opção de implantação**              | Nuvem |
| **Status**                         | **Preterido:** esse recurso foi totalmente substituído por implantações de autoatendimento. |

### <a name="visual-studio-2015"></a>Visual Studio2015

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Para dar suporte às versões mais recentes do Visual Studio, algumas alterações devem ser feitas nas extensões X++ para Visual Studio. Essas alterações são incompatíveis com o Visual Studio 2015. |
| **Substituída por outro recurso?**   | O Visual Studio 2017 substituirá o Visual Studio 2015 como a versão implantada e necessária. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | Depois que a disponibilidade de novas máquinas virtuais (VMs) com o Visual Studio 2017 for anunciada, as VMs existentes que tiverem somente o Visual Studio 2015 precisarão ser reimplantadas pelo do ciclo de lançamentos 1 de 2021. |

### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos contendo referências de campo inválidas

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os grupos de campos nas definições de metadados da tabela podem conter referências de campo inválidas. Se esses grupos de campos forem implantados, eles pode causar falhas de tempo de execução no Financial Reporting e no Microsoft SQL Server Reporting Services (SSRS). A atualização de plataforma 23 apresentou um *aviso* do compilador que permitiu que esse problema de metadados fosse solucionado. As atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations categorizam esse problema como um *erro* do compilador.<p>Para corrigir esse problema, siga estas etapas.</p><ol><li>Remova a referência de campo inválida da definição do grupo de campos da tabela.</li><li>Recompilar.</li><li>Certifique-se de que os erros sejam solucionados.</li></ol> |
| **Substituída por outro recurso?**   | Este erro do compilador substitui permanentemente o aviso do compilador.  |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | **Preterido:** o aviso do compilador é um erro de compilador nas atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licenças ISV criadas usando o algoritmo de hash SHA1

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | O processo para criar licenças de fornecedor independente de software (ISV) foi alterado. Para obter mais informações, consulte o [Licenciamento de fornecedor independente de software (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **Substituída por outro recurso?**   | Sim. Use o Windows PowerShell para criar licenças. |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | <strong>Preterido</strong> : Licenças ISV criadas usando o algoritmo de hash SHA1. Esse algoritmo dependia de certificados que eram criados usando o utilitário MakeCert, e esse utilitário foi preterido.<p><strong>Preterido</strong> : O uso de SHA1 para fins de segurança ou hash. O funcionamento do SHA1 será descontinuado no início de 2021. Portanto, não deve mais ser usado.<p><strong>Removido:</strong> Suporte para solicitações de entrada ou saída do Transport Layer Security (TLS) 1.0 e TLS 1.1. |

## <a name="platform-update-32"></a>Update 32 para plataforma

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>Caixa de diálogo Alterar solicitação de fluxo de trabalho não inclui mais a seleção do usuário de lista suspensa
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Isso foi um problema de segurança, pois a solicitação de alteração poderia ser enviada para um usuário indesejado. Isso também era um problema de usabilidade porque forçava o usuário a determinar quem foi o originador do fluxo de trabalho e selecioná-los manualmente.  |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Fluxo de Trabalho |
| **Opção de implantação**              | Todas |
| **Status**                         | A lista suspensa de seleção de usuário foi removida da caixa de diálogo alteração de solicitação na atualização de plataforma 32. Solicitações de alteração de solicitação serão enviadas automaticamente para o originador conforme pretendido. Para obter mais informações sobre essa funcionalidade, consulte [Ações em processos de aprovação de fluxo de trabalho](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Links de detalhamento incorporados não são mais compatíveis em documentos paginados renderizados pelo serviço armazenado em nuvem 
|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | As URLs de navegação inseridas nos documentos processados pelo serviço podem conter dados comerciais confidenciais. Estamos removendo o suporte para links de detalhamento incorporados em documentos como uma precaução de segurança para proteger ainda mais os dados dos clientes. Os usuários também se beneficiarão do melhor desempenho enquanto produzem documentos interativamente como resultado dessa alteração.  |
| **Substituída por outro recurso?**   | Não |
| **Áreas afetadas do produto**         | Relatório |
| **Opção de implantação**              | Todas |
| **Status**                         | Este recurso está sendo removido ativamente do serviço.<br><br>O cliente moderno oferece várias opções para produzir exibições que incluem links gerados automaticamente para ajudar na navegação do aplicativo. Os documentos paginados processados pelo serviço são recomendados para comunicações externas enviadas por email, arquivadas e impressas para os destinatários. Aperfeiçoamos a experiência de visualização de documentos diretamente no navegador, que oferece acesso direto a impressoras locais. Para obter mais informações, consulte [Visualização de documentos em PDF com um visualizador incorporado](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Comunicados anteriores sobre recursos removidos ou obsoletos
Para saber mais sobre os recursos que foram removidos ou preteridos em versões anteriores, consulte [Recursos removidos ou obsoletos em versões anteriores](../migration-upgrade/deprecated-features.md).

