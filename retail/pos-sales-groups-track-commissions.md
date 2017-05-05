---
title: "Rastrear comissões em PDV usando grupos de vendas"
description: "É uma prática comum de varejo rastrear as vendas associadas pelo associado que trabalhou com o cliente, fornecendo ajuda, venda direta, venda cruzada e processamento da transação."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: dfefdede8f3bc884b230109d6c915127a1361ecd
ms.lasthandoff: 03/31/2017


---

# <a name="track-commissions-in-pos-using-sales-groups"></a>Rastrear comissões em PDV usando grupos de vendas

[!include[banner](includes/banner.md)]


É uma prática comum de varejo rastrear as vendas associadas pelo associado que trabalhou com o cliente, fornecendo ajuda, venda direta, venda cruzada e processamento da transação.

Rastrear vendas por representantes de vendas é uma medida das habilidades de venda dos associados, enquanto as vendas por caixa é uma medida de aceleração e eficiência. Vendas rastreadas por representantes de vendas também são frequentemente usadas para calcular comissões ou outros incentivos.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Como configurar um trabalhador como um representante de vendas no PDV
Quando um trabalhador é adicionado a um grupo de vendas, ele torna-se elegível para comissão e pode ser identificado como um representante de vendas no sistema. Um trabalhador que não esteja em um grupo de vendas não foi qualificado para a comissão e não será listado como representante de vendas no aplicativo PDV. No PDV, a lista de representantes de vendas é derivada de todos os grupos de vendas que contêm pelo menos um trabalhador atribuído à loja. A lista é exibida no PDV como uma combinação da ID de grupo de vendas e de nome (ID : Name). Um grupo de vendas padrão pode ser atribuído a trabalhadores para ajudar em cenários onde o varejista escolhe definir o representante de vendas em linhas de PDV automaticamente. Os usuários podem selecionar de qualquer grupo de vendas do qual o trabalhador é membro.

## <a name="functionality-profile-settings"></a>Configurações de perfil funcionais
Há várias configurações de perfil funcionais para um loja que determinarão o fluxo e processo no PDV que envolve representantes de vendas.

|                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Perfil**                           | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Padrão para caixa quando disponível** | Se esta opção for habilitada, o PDV preencherá automaticamente as linhas de transação com o grupo de vendas padrão do caixa atual. Se um caixa não tiver um grupo de vendas padrão especificado, o valor não será definido. Um usuário ainda poderá definir manualmente o grupo de vendas usando um botão da grade de botão de PDV.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Solicitar representante de vendas**   | Essa opção tem três valores possíveis: **Não** - Se essa opção for selecionada, o usuário não será avisado para selecionar um grupo de vendas. O valor ainda pode ser definido usando um grupo de vendas padrão do caixa ou manualmente usando um botão da grade de botão de PDV. **Início da transação** - Se essa opção estiver selecionada, e a opção **Padrão para caixa** não está habilitada ou o caixa atual não tem um grupo de vendas padrão, o usuário será avisado para selecionar um grupo de vendas no começo de cada transação. Selecionar um grupo de vendas deste aviso deixará padrão todas as linhas subsequentes ao grupo de vendas selecionado. Um usuário ainda poderá definir manualmente o grupo de vendas usando um botão da grade de botão de PDV. **Para cada linha** - Se essa opção estiver selecionada, e a opção **Padrão para caixa** não está habilitada ou o caixa atual não tem um grupo de vendas padrão, o usuário será avisado para selecionar um grupo de vendas adicionando cada linha. Um usuário ainda poderá definir manualmente o grupo de vendas usando um botão da grade de botão PDV. |
| **Requer**                           | Esta opção só é aplicável quando o PDV é configurado para solicitar um representante de vendas. Se habilitado, o usuário precisará escolher um grupo de vendas antes de continuar. Se não, o usuário será avisado, mas poderá cancelar e continuar sem fazer uma seleção. Depois da linha ser adicionada, um usuário com permissões suficientes ainda poderá remover o grupo de vendas da linha. “Exigir representante de vendas” não é imposto nessa situação.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Como exibir informações do representante de vendas na tela de transação do PDV
O layout e os conteúdos da tela de transação do PDV são configuráveis usando o designer de layout da tela e layouts de tela atribuídos às lojas, registros ou trabalhadores. O campo **Representante de vendas** pode ser adicionado à guia Linhas do painel Recebimento.  Isso exibirá a ID do grupo de vendas específico de cada linha na tela de transação.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Como adicionar operações de representante de vendas a grades de botão do PDV
O PDV permite ao usuário configurar grades de botão, que são incluídas em layouts de tela para fornecer acesso a operações de PDV. As seguintes operações de PDV podem ser atribuídas aos botões de grade de botão que estão relacionados aos representantes de vendas.

|                                           |                                                                                                                                                                                                                                                                                              |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Operação**                             | **Descrição**                                                                                                                                                                                                                                                                              |
| Definir representante de vendas na linha          | Esta operação de PDV exibe uma lista de grupos de vendas elegíveis (ID: Nome da loja) para a loja. Selecionar um grupo de vendas desta lista definirá o valor na linha de transação atual.                                                                                                            |
| Limpar representante de vendas na linha        | Esta operação de PDV remove o valor do grupo de vendas atual da linha de transação atual.                                                                                                                                                                                                  |
| Definir representante de vendas na transação   | Esta operação de PDV exibe uma lista de grupos de vendas elegíveis (ID: Nome da loja) para a loja. Selecionar um grupo de vendas desta lista definirá o valor padrão na transação atual. Qualquer linha existente sem um grupo de vendas atribuído será definido, assim como quaisquer linhas adicionadas subsequentemente. |
| Limpar representante de vendas na transação | Esta operação de PDV remove o valor do grupo de vendas padrão atual da transação atual. Não impacta quaisquer linhas já existentes na transação.                                                                                                                             |

## <a name="calculating-commissions"></a>Como calcular comissões
A comissão é calculada para os trabalhadores nos grupos de vendas específicos no momento lançamento de demonstrativo ou lançamento de ordem de venda. O valor da comissão é determinado com base no compartilhamento de comissões de trabalhador, como definido no grupo de vendas e as configurações de cálculo de comissão associados para o cliente e/ou produtos na transação.



