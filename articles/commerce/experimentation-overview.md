---
title: Experimentação no Dynamics 365 Commerce
description: A experimentação habilita a criação, a edição e o gerenciamento do layout de página e dos tratamentos de conteúdo no construtor de sites. O suporte de experimentação de ponta a ponta é habilitado para páginas e entidades de comércio eletrônico em uma página.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 85eb7a661cc66c42699797cca4fa6820941de7c0
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4410328"
---
# <a name="experimentation-in-dynamics-365-commerce"></a>Experimentação no Dynamics 365 Commerce
Use a experimentação no Dynamics 365 Commerce para validar hipóteses sobre a efetividade das suas páginas de comércio eletrônico e tome decisões com a confiança controlada por dados. O Commerce oferece suporte a testes A/B em páginas, módulos e fragmentos e permite que você meça o impacto das alterações propostas no seu site.

Você pode criar, editar e gerenciar tratamentos de conteúdo e de página, conhecidos como **variações** no construtor de sites do Commerce. O Commerce é integrado a serviços de terceiros que você pode usar para criar experimentos e atribuições de tratamento. Os fluxos de eventos em tempo real capturados no Commerce habilitam a análise que define os resultados da experimentação no serviço de terceiros. Em seguida, você pode aproveitar essas análises para ajudar a dar suporte ou refutar sua hipótese.

## <a name="set-up-prerequisites"></a>Pré-requisitos de configuração
1. **Obter a versão correta do Commerce** - atualize sua biblioteca de módulos, o SDK (kit de desenvolvimento de software) de extensibilidade de canal online e a Commerce Scale Unit para o Commerce versão 10.0.13 ou posterior.
1. **Configurar um conector de experimentação** - um conector de experimentos permite que o Commerce conecte com serviços de terceiros para recuperar a lista de experimentos e determinar quando mostrar um experimento para um usuário. Você pode adquirir um conector de terceiros do [AppSource](https://appsource.microsoft.com). Siga as instruções de configuração fornecidas pelo editor. Como alternativa, você pode usar o conector de teste de exemplo do Commerce para testar o fluxo de trabalho de experimentação sem a necessidade de configurar um serviço externo. Para obter mais informações, consulte [Configurar e habilitar conectores](e-commerce-extensibility/connectors.md). 
1. **Ativar sinalizadores do recurso de experimentação no Commerce** - é possível habilitar a experimentação no nível do locatário em **Configurações de Locatário > Recursos** ou no nível do site, em **Configurações do Site > Recursos**.
    - Habilite o sinalizador **Experimentação** para criar variações de experimentos de módulos em uma página sem afetar ou copiar outros conteúdos que não fazem parte do experimento. Isso garante que atualizações de conteúdo contínuas fora do experimento permaneçam sincronizadas durante o ciclo de vida de experimento. A desabilitação deste sinalizador impedirá que todos os experimentos sejam mostrados para os usuários e removerá todas as funções de edição no construtor de sites.
    - Habilite o sinalizador **Experimento em páginas ou fragmentos** para executar experimentos em uma página ou fragmento. Isso cria uma cópia de instância completa da página inteira ou fragmento para todos os módulos na página ou fragmento. Use este modo quando quiser testar alterações de conteúdo abrangentes ou onde a sincronização de alterações de conteúdo contínua nas instâncias não for uma preocupação. Desabilitar esse sinalizador impede a criação e a edição de novos experimentos em páginas e fragmentos.
    > [!NOTE]
    > O sinalizador **Experimentação** também deve ser habilitado para que a funcionalidade **Experimento em páginas ou fragmentos** funcione.
    
## <a name="experimentation-lifecycle"></a>Ciclo de vida da experimentação
A configuração de um experimento, a criação de variações e a execução de um experimento é um processo iterativo. O diagrama a seguir ilustra o ciclo de vida de experimentação no Commerce e no serviço de terceiros. 

[ ![Ciclo de vida da experimentação](./media/experimentation_lifecycle.svg) ](./media/experimentation_lifecycle.svg#lightbox)

Para saber mais sobre cada etapa do processo de experimentação, consulte os tópicos a seguir.
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