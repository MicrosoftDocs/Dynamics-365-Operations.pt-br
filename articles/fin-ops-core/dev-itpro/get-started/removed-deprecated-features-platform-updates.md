---
title: Recursos de plataforma removidos ou obsoletos
description: Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção nas atualizações de plataforma do Finance and Operations apps.
author: sericks007
manager: AnnBe
ms.date: 04/13/2020
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
ms.openlocfilehash: 0072ca507301fdb880f0595a06377ff01366ca20
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2020
ms.locfileid: "3260520"
---
# <a name="removed-or-deprecated-platform-features"></a>Recursos de plataforma removidos ou obsoletos

[!include [banner](../includes/banner.md)]

Este tópico descreve os recursos que já foram removidos ou foram planejados para remoção nas atualizações de plataforma do Finance and Operations apps.

- Um recurso *removido* não estará mais disponível no produto.
- Um recurso *preterido* não está no desenvolvimento ativo e poderá ser removido em uma atualização futura.

Esta lista é destinada a ajudá-lo a considerar essas remoções e reprovações para seu próprio planejamento. 

> [!NOTE]
> Informações detalhadas sobre objetos no Finance and Operations apps podem ser encontradas nos [Relatórios de referência técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Você pode comparar as diferentes versões desses relatórios para aprender sobre objetos que foram alterados ou removidos em cada versão do Finance and Operations apps.

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations

### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos contendo referências de campo inválidas

|   |  |
|------------|--------------------|
| **Motivo para a reprovação/remoção** | Os grupos de campos nas definições de metadados da tabela podem conter referências de campo inválidas. Se esses grupos de campos forem implantados, eles pode causar falhas de tempo de execução no Financial Reporting e no Microsoft SQL Server Reporting Services (SSRS). A atualização de plataforma 23 apresentou um *aviso* do compilador que permitiu que esse problema de metadados fosse solucionado. As atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations categorizam esse problema como um *erro* do compilador.<p>Para corrigir esse problema, siga estas etapas.</p><ol><li>Remova a referência de campo inválida da definição do grupo de campos da tabela.</li><li>Recompilar.</li><li>Certifique-se de que os erros sejam solucionados.</li></ol> |
| **Substituída por outro recurso?**   | Este erro do compilador substitui permanentemente o aviso do compilador.  |
| **Áreas afetadas do produto**         | Ferramentas de desenvolvimento do Visual Studio |
| **Opção de implantação**              | Todas |
| **Status**                         | **Preterido** : O aviso do compilador agora é um erro de compilador nas atualizações de plataforma para a versão 10.0.11 dos aplicativos do Finance and Operations. |

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

