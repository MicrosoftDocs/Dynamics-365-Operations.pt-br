---
title: "Comissões do faixa POS usando grupos de vendas"
description: "É uma prática comum POS por rastrear vendas associado que trabalhou com a ajuda de entrega, acima- vendendo, e vendendo entre processando a transação."
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

# <a name="track-commissions-in-pos-using-sales-groups"></a>Comissões do faixa POS usando grupos de vendas

É uma prática comum POS por rastrear vendas associado que trabalhou com a ajuda de entrega, acima- vendendo, e vendendo entre processando a transação.

Rastrear vendas por representantes de vendas é uma medição de associa vendendo habilidades, quando as vendas pelo caixa uma medição de velocidade e de eficiência. Vendas rastreadas por representantes de vendas também são freqüentemente usadas calcular comissões ou outros incentivos.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Configurando um trabalhador como um representante de vendas no POS
Quando um trabalhador é adicionado a um grupo de vendas, tornam-se qualificáveis da comissão e podem ser identificado como representante de vendas no sistema. Um trabalhador que não esteja em um grupo de vendas não foi qualificado para a comissão e não será listado como representante de venda no aplicativo (POS) do ponto de venda. POS, Na lista de vendas de representantes deriva de todos os grupos de vendas que contêm o menos um trabalhador atribuída à loja. A lista é exibida no POS como uma combinação da ID de grupo de vendas e de nome (ID: Nome.) Um grupo de vendas padrão pode ser atribuído para trabalhadores a cenários suporte do fornecedor onde escolher para definir automaticamente o representante de vendas no POS. Os usuários podem selecionar de qualquer grupo de vendas que o trabalhador é membro.

## <a name="functionality-profile-settings"></a>Configurações de perfil de funcionalidade
Há várias configurações de perfil da funcionalidade de um armazenamento que determine o fluxo e o processo em retail envolvendo representantes de vendas.

|                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Profile**                           | **Description**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Default to cashier when available** | Se esta opção for habilitada, o retail preencherá automaticamente linhas de transação com o grupo de vendas padrão atual de caixa. Se um caixa não tiver um grupo de vendas padrão especificado, o valor não será definido. Um usuário poderá definir manualmente ainda para o grupo de vendas usando um botão da grade de botões POS.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Prompt for sales representative**   | Ela tem três valores possíveis: ** Nenhum ** - se essa opção for selecionada, o usuário não será solicitado a selecionar um grupo de vendas. O valor não pode ser definido com o grupo de vendas padrão em um caixa ou manualmente usando um botão da grade de botões POS. ** O início da transação ** - se essa opção for selecionada, ou ** padrão o caixa ** a opção não for habilitado atual ou a caixa não tiver um grupo de vendas padrão, o usuário será solicitado para um grupo de vendas no início de cada transação. Selecionando um grupo de vendas deste prompt padrão as linhas subsequentes ao grupo de vendas. Um usuário poderá definir manualmente ainda para o grupo de vendas usando um botão da grade de botões POS. ** ** Para cada linha - se essa opção for selecionada, ou ** padrão o caixa ** a opção não estiver habilitada ou o caixa atual não tiver um grupo de vendas padrão, o usuário será solicitado para um grupo de vendas depois de ter adicionado cada linha. Um usuário poderá definir manualmente ainda para o grupo de vendas usando um botão da grade de botões POS. |
| ** Exige **                           | Esta opção só é aplicável quando o retail é configurado para solicitar um representante de vendas. Se habilitado, ele deverá escolher um grupo de vendas antes de continuar. Se não, o usuário será solicitado, mas pode cancelar e continuar sem fazer uma seleção. Depois que a linha for adicionada, um usuário com permissões suficientes ainda pode remover o grupo de vendas da linha. “Exige o representante de vendas” não é imposto nessa situação.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Exibindo informações do representante de vendas na tela da transação POS
O layout e os conteúdos de tela da transação POS são configuráveis usando o designer do layout da tela e layouts de tela atribuídos às lojas, os registros, ou a funcionários. ** Representante de vendas ** o campo pode ser adicionado linhas guia do painel de recebimento.  Isso exibe a ID do grupo de vendas especificada para cada linha na tela da transação.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Adicionando representante de vendas POS em operações abotoam grades
POS permite que os usuários configurem as grades de botões, incluídas em layouts de tela para fornecer acesso operações POS. As seguintes operações POS podem ser atribuídas aos botões da grade de botões que se referem representantes de vendas.

|                                           |                                                                                                                                                                                                                                                                                              |
|-------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Operação**                             | **Description**                                                                                                                                                                                                                                                                              |
| Definir representante de vendas na linha          | Esta operação POS exibe uma lista de grupos qualificáveis de venda (ID: Nome da loja). Selecione um grupo de vendas desta lista definirá o valor na linha de transação atual.                                                                                                            |
| Limpar representante de vendas na linha        | Esta operação POS remove o valor do grupo atual de venda da linha de transação atual.                                                                                                                                                                                                  |
| Definir o representante de vendas na transação   | Esta operação POS exibe uma lista de grupos qualificáveis de venda (ID: Nome da loja). Selecione um grupo de vendas desta lista definirá o valor padrão na transação. Todas as linhas existentes sem um grupo de vendas atribuído serão definidas, bem como as linhas adicionadas posteriormente. |
| Representante de vendas for compensado na transação | Esta operação POS remove o valor do grupo atual de venda da transação atual. Não tem nenhuma linhas que já existem na transação.                                                                                                                             |

## <a name="calculating-commissions"></a>Calcular comissões
A comissão é calculada para trabalhadores os especificados em grupos de vendas no momento de postagem de demonstrativo ou de postagem de ordem de venda. O valor da comissão é determinado com base no compartilhamento de comissões de trabalhador, como definido no grupo de vendas associadas e as configurações de cálculo de comissão para o cliente e/ou os produtos na transação.


