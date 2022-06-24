---
title: Experimentação no Dynamics 365 Commerce
description: A experimentação habilita a criação, a edição e o gerenciamento do layout de página e dos tratamentos de conteúdo no construtor de sites. O suporte de experimentação de ponta a ponta é habilitado para páginas e entidades de comércio eletrônico em uma página.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: overview
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1ef877072ba7ffe1b0326cf8d526b512b5ab30b8
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946192"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Experimentação no Dynamics 365 Commerce
Use a experimentação no Dynamics 365 Commerce para validar hipóteses sobre a efetividade das suas páginas de comércio eletrônico e tome decisões com a confiança controlada por dados. O Commerce oferece suporte a testes A/B em páginas, módulos e fragmentos e permite que você meça o impacto das alterações propostas no seu site.

Você pode criar, editar e gerenciar tratamentos de conteúdo e de página, conhecidos como **variações** no construtor de sites do Commerce. O Commerce é integrado a serviços de terceiros que você pode usar para criar experimentos e atribuições de tratamento. Os fluxos de eventos em tempo real capturados no Commerce habilitam a análise que define os resultados da experimentação no serviço de terceiros. Em seguida, você pode aproveitar essas análises para ajudar a dar suporte ou refutar sua hipótese.

## <a name="set-up-prerequisites"></a>Pré-requisitos de configuração

1. **Obter a versão correta do Commerce** - atualize sua biblioteca de módulos, o SDK (kit de desenvolvimento de software) de extensibilidade de canal online e a Commerce Scale Unit para o Commerce versão 10.0.13 ou posterior.
1. **Configurar um conector de experimentação** - um conector de experimentos permite que o Commerce conecte com serviços de terceiros para recuperar a lista de experimentos e determinar quando mostrar um experimento para um usuário. Você pode adquirir um conector de terceiros do [AppSource](https://appsource.microsoft.com). Siga as instruções de configuração fornecidas pelo editor. Como alternativa, você pode usar o conector de teste de exemplo do Commerce para testar o fluxo de trabalho de experimentação sem a necessidade de configurar um serviço externo. Para obter mais informações, consulte [Configurar e habilitar conectores](e-commerce-extensibility/connectors.md). 
1. **Ativar sinalizadores do recurso de experimentação no Commerce** - é possível habilitar a experimentação no nível do locatário em **Configurações de Locatário \> Recursos** ou no nível do site, em **Configurações do Site \> Recursos**. Ative o sinalizador de **Experimentação** para começar a criar variações de módulo. A desabilitação deste sinalizador impedirá que todos os experimentos sejam mostrados para os usuários e removerá todas as funções de edição no construtor de sites.
    
## <a name="experimentation-lifecycle"></a>Ciclo de vida da experimentação

A configuração de um experimento, a criação de variações e a execução de um experimento é um processo iterativo. O diagrama a seguir ilustra o ciclo de vida de experimentação no Commerce e no serviço de terceiros. 

[ ![Ciclo de vida da experimentação.](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Para saber mais sobre cada etapa do processo de experimentação, consulte os artigos a seguir.
- [Identificar uma hipótese e determinar as métricas para um experimento](experimentation-identify.md)
- [Configurar um experimento](experimentation-setup.md)
- [Conectar e editar um experimento](experimentation-connect-edit.md)
- [Visualizar e publicar um experimento](experimentation-preview-publish.md)
- [Executar e monitorar um experimento](experimentation-run-monitor.md)
- [Promover uma variação e concluir um experimento](experimentation-review-complete.md)

> [!NOTE]
> Para saber onde um experimento está no ciclo de vida, selecione **Experimentos** no painel de navegação esquerdo do construtor de sites. Uma lista de experimentos é exibida com o status de cada experimento no Commerce e no serviço de terceiros. Para obter mais informações, consulte [Analisar o status de um experimento](experimentation-status.md).

## <a name="next-step"></a>Próxima etapa
[Identificar uma hipótese e determinar as métricas de sucesso para um experimento](experimentation-identify.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
