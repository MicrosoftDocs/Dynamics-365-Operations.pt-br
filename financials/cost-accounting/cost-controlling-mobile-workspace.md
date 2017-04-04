---
title: "O espaço de trabalho móvel de controle de custo estimado para Microsoft Dynamics 365 para o descritivo de operações"
description: "Com espaço de trabalho móvel de controle de custo previsto, gerentes de centro de custo podem consultar o desempenho de centro de custos a qualquer momento e em qualquer lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>O espaço de trabalho móvel de controle de custo estimado para Microsoft Dynamics 365 para o descritivo de operações

Com espaço de trabalho móvel de controle de custo previsto, gerentes de centro de custo podem consultar o desempenho de centro de custos a qualquer momento e em qualquer lugar. 

<a name="prerequisites"></a>Pré-requisitos
-------------

| Pré-requisito                                                         | descrição                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Leia sobre o Microsoft Dynamics 365 para o preparo de celular de operações | [Dynamics 365 para a plataforma móvel] operações (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Verifique se está usando um ambiente com Microsoft Dynamics 365 para a versão 1611 de operações e o Microsoft Dynamics para atualização 3 de preparo operações (). em novembro de 2016 |
| 3215650 KB de Hotfix                                                    | Instalar o hotfix para habilitar espaços de trabalho fornecidos no Microsoft Dynamics 365 para as operações.                                                                       |
| Dispositivo móvel que tem o dynamics 365 para o descritivo instalado de operações | Baixe o dynamics 365 para o descritivo de operações do armazenamento móvel descritivo.                                                                                                      |

## <a name="introduction"></a>Introdução
O espaço de trabalho móvel de controle de custo previsto fornece uma exibição instantânea de desempenho atual centros de custos comparar custos reais com os custos orçados. Você pode fazer busca detalhada nos elementos status previsto de custo individuais.

### <a name="example"></a>Exemplo

Um funcionário receber um convite para uma internacional. conferência A organização que terá cobrir todas despesas de viagem. O funcionário pede sua comedoiro se possível. a assistir conferência O gerenciador abre rapidamente o espaço de trabalho móvel de controle de custo estimado no telefone móvel para consultar se tiver o orçamento para o funcionário. a assistir conferência

### <a name="data-security"></a>Segurança de dados

Os dados no espaço de trabalho de controle de custo previsto são protegidos por suas credenciais. É permitido apenas a gerente do centro de custos consulte dados para seu próprio centro de custos. A segurança em nível de acesso será gerenciada no módulo de contabilização de custo previsto. Contadores de custo define a configuração móvel de controle de custo previsto do espaço de trabalho no módulo contabilização de custo previsto. Depois do espaço de trabalho for publicado Microsoft Dynamics 365 para o descritivo de operações, está disponível em dynamics 365 do celular descritivo de operações. Isso garante que os gerentes de centro de custos na organização olhem dados no mesmo formato.

### <a name="actions-views-and-links"></a>Exibições, ações, e links

O espaço de trabalho móvel de controle de custo previsto para dynamics 365 para o descritivo de operações fornece as seguintes ações, e links, exibições:

-   Ações 
    -   ** Selecione configurações ** escolher um layout.
    -   ** Selecione custo objetos ** para escolher os centros de custo em que você deseja filtrar dados. ** Observação: ** A lista será exibida conforme o acesso concedido no módulo contabilização de custo previsto.

<!-- -->

-   Com base em selecionados abaixo ** ações ** e o que é configurado no módulo contabilização de custo previsto, você pode exibir as seguintes informações em cartões. Observe que o valor é exibido no mesmo formato: Real, orçamento, variação, e variação %. 
    -   Real versus orçamento o período (atual)
    -   O orçamento real vs revisado período (atual)
    -   O orçamento real vs (período anterior)
    -   O orçamento real vs revisado (período anterior)
    -   O orçamento real vs (ano até)
    -   O orçamento real vs revisado (ano até)

<!-- -->

-   Links
    -   Detalhes do período atual.
    -   Detalhes do período anterior.
    -   Detalhes ano até.

Quando você seleciona um de links, as fichas por elementos de custo previsto será exibido. O valor em cartões é exibido neste formato: Real, orçamento, variação de orçamento, variação de porcentagem revisou orçamento, o orçamento, a variação revisada de orçamento, a variação de orçamento revisada %.  [![que controla (]. /media/cost-controlling.png)](. /media/cost-controlling.png)

## <a name="get-started"></a>Introdução
Rastrear essas etapas para introdução descritivo móvel usando o controle de custos no dispositivo móvel.

1.  No armazenamento móvel descritivo, baixar e instalar o Microsoft Dynamics 365 para o descritivo de operações.
2.  Inicie a descritivo no dispositivo.
3.  Insira a URL do 365.
4.  Insira a empresa para conectar-se. Por exemplo, insira USMF ** **.
5.  A primeira vez que que se conectar, será solicitado para o nome de usuário e a senha para o Microsoft Dynamics 365 para a conta de operações. Insira suas credenciais. Depois que se conectar, verá espaços de trabalho disponíveis para sua empresa.

Exibir espaços de trabalho do celular descritivo, primeiramente publicar espaços de trabalho o dynamics desejados para o 365 descritivo de operações.

1.  Dynamics 365 Inicial para as operações.
2.  Ir ** administração de sistema ** &gt; ** de instalação ** &gt; ** ** parâmetros do sistema.
3.  Selecione ** gerenciamento descritivo móvel **.
4.  Selecione o espaço de trabalho ** custo o controle ** publicar a plataforma móvel.
5.  ** Publicar selecione o espaço de trabalho. **
6.  Atualizar o dispositivo para consultar espaços de trabalho publicados.

## <a name="view-the-performance-of-your-cost-center"></a>Exibir desempenho do centro de custo
1.  No dispositivo móvel, selecione custo ** o controle ** o espaço de trabalho.
2.  ** Selecionar o controle de custo ** objeto.
3.  Clique ** ** ações.
4.  Clique ** ** selecione configuração para selecionar um layout de controle de custo previsto.
5.  Click **Done**.
6.  Clique ** ** ações.
7.  Clique ** objeto de custo previsto selecione ** selecione os centros de custos ao qual foi concedido acesso.
8.  Click **Done**.
9.  Exibir desempenho total do centro de custos.
10. Clique ** detalhes para o período atual. **
11. Exibir desempenho elementos de custo previsto individuais.
12. Também é possível pesquisar para elementos de custo previsto específicos.



