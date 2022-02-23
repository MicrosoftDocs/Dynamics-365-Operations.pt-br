---
title: Criar um novo layout de depósito
description: Este tópico descreve como configurar informações sobre as localizações em um depósito.
author: perlynne
manager: tfehr
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, DefaultDashboard, InventLocation, WMSLocationWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 09666e95cc90913f1bf8555b9ff2c48aa55369ed
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422448"
---
# <a name="create-a-new-warehouse-layout"></a>Criar um novo layout de depósito

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar informações sobre as localizações em um depósito. Aplica-se apenas a depósitos criados usando o "armazenamento básico” no módulo de gerenciamento de estoque, não a depósitos criados no módulo de gerenciamento de depósito. Você pode usar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="set-the-default-location-capacity"></a>Definir a capacidade do local padrão
1. No Painel de Navegação, vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque**.
2. Selecione a guia **Localizações**.
3. No campo **Largura padrão**, digite um número.
4. No campo **Profundidade padrão**, insira um número.
5. No campo **Altura padrão**, insira um número.
6. Selecione **Salvar**.
7. Feche a página.

## <a name="define-the-location-name-format"></a>Definir o formato do nome da localização
1. No Painel de Navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Divisão de estoque > Depósitos**.
2. Selecione **Novo**.
3. No campo **Depósito**, digite um valor.
4. No campo **Nome**, digite um valor.
5. No campo **Site**, selecione o registro desejado na pesquisa.
6. Alternar a expansão da seção **Nomes de local**. As opções nesta seção definem o formato padrão para nomes da localização. Em nosso exemplo, incluiremos o número do corredor, o número do rack e o número da prateleira.  
7. Defina a opção **Incluir corredor** como **Sim**.
8. Defina a opção **Incluir rack** como **Sim**. 
9. No campo **Formato**, digite o valor para o rack.
10. Defina a opção **Incluir prateleira** como **Sim**.
11. No campo **Formato**, digite o valor para a prateleira.

## <a name="define-warehouse-locations"></a>Definir locais de depósito
1. No Painel de Ações, selecione **Depósito**.
2. Selecione **Assistente de Localização**.
3. Selecione **Avançar**.
4. Desmarque a opção **Docas de saída**
5. Desmarque a opção **Locais de massa**
6. Selecione **Avançar** até chegar à opção de selecionar **Concluir**.
7. Feche a página.
8. Atualize a página.

