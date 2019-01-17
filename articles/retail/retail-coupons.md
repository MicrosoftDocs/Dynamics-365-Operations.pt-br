---
title: Configurar cupons para vendas de varejo
description: "Este tópico fornece uma visão geral de cupons de varejo e explica como defini-los."
author: scott-tucker
manager: AnnBe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailCoupon, RetailParameters, RetailSharedParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.search.region: Global
ms.search.industry: retail
ms.author: scotttuc
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: bd3596b6c78c5959ca289c73bcc5785eb770be39
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="set-up-coupons-for-retail-sales"></a>Configurar cupons para vendas de varejo

[!include [banner](includes/banner.md)]

## <a name="overview-of-coupons"></a>Visão geral de cupons

Os cupons são códigos e códigos de barras que são usados ​​para adicionar descontos de varejo às transações. Cada cupom pode ter vários códigos, e cada código pode ter suas próprias datas efetivas.

Cada cupom é relacionado a um desconto de varejo. Os grupos de preços associados ao desconto definem os clientes que podem usar um cupom ou os canais onde um cupom é válido.

Essencialmente, os cupons são validação adicional sobre os descontos de varejo. O cupom fornece os códigos de cupom e os códigos de barra que são necessários, juntamente com os intervalos de datas para esses códigos. O cupom também fornece limites de uso opcionais e propriedades exigidas pelo cliente. O desconto fornece o conjunto de produtos para o qual o cupom é válido. Os grupos de preços para o desconto fornecem o conjunto de clientes, canais ou catálogos para os quais o cupom é válido.

Para criar um cupom, você cria o desconto e o cupom separadamente. Em seguida, você os vincula selecionando o desconto na página do cupom no Microsoft Dynamics 365 para varejo.

> [!NOTE]
> Após um cupom se vinculado a um desconto, vários campos na página de desconto no Microsoft Dynamics 365 for Retail se tornarão somente leitura, pois eles são gerenciados pelas configurações do cupom. Esses campos incluem os campos para o status e os intervalos de datas padrão.

### <a name="limited-use-coupons"></a>Cupons de uso limitado

Os cupons podem ser configurados como cupons de uso limitado. O limite de uso pode ser definido por cliente ou canal, ou como um limite global. Este limite é aplicado quando o código ou o código de barras são inseridos ou digitalizados no POS ou durante a entrada da ordem do cliente.

O limite é aplicado por código de cupom em um cupom. Por exemplo, um cupom de uso único que possui dois códigos de cupom pode ser usado duas vezes: uma vez por cada código de cupom. Cada código em um cupom pode ser definido de forma independente como ativo.

> [!NOTE]
> Depois que um código de cupom atingiu seu limite de uso, o sistema *não* alterará automaticamente o status do código de cupom “Usado”. Entretanto, o sistema não permitirá o uso adicional de um código de cupom que atingiu seu limite de uso. Se o status de um código de cupom está definido manualmente como algo diferente de “Ativo”, o código de cupom não pode ser usado em nenhum canal.

## <a name="managing-coupons"></a>Gerenciando cupons

Você deve criar o desconto e o cupom separadamente. Em seguida, vincule-os selecionando o desconto na página do cupom. Depois de vincular um cupom a um desconto, vários campos para o desconto tornam-se somente leitura, pois são gerenciados pelas configurações do cupom. Esses campos incluem os campos para o status e os intervalos de datas padrão.

Essencialmente, os cupons agora são validação adicional sobre os descontos de varejo. O cupom fornece códigos de cupom e códigos de barras, juntamente com intervalos de datas, os limites de uso e a propriedade exigida pelo cliente. O desconto fornece o conjunto de produtos para o qual o cupom é válido. Os grupos de preços de desconto fornecem o conjunto de clientes, canais ou catálogos para os quais o cupom é válido.

## <a name="system-setup-for-coupons"></a>Configuração do sistema para cupons

Antes de configurar um cupom, você deve configurar o código da barra de cupom e duas sequências de números de cupom.

1. Na página **Caracteres de máscara**, crie um novo caractere de máscara para o código de cupom. Você pode selecionar qualquer caractere não utilizado.
2. Na página **Configuração de máscara de código de barras**, crie uma nova a máscara de código de barras. Defina o campo **Tipo** como **Cupom**.
3. Na página **Configuração de código de barras**, crie um novo código de barras que usa a máscara de código de barras que você criou.
4. Na página **Sequências numéricas**, crie duas novas sequências numéricas. Uma sequência é para a ID do código de cupom, e outra sequência for para o número de cupom. A ID do código de cupom é o identificador exclusivo para cada código de cupom para um cupom. O número do cupom é o identificador exclusivo do cupom. Cada cupom pode ter vários códigos e os códigos de barras que disparam um cupom.

    > [!NOTE]
    > Para ambas as sequências numéricas, você deve definir o campo **Escopo** como **Empresa**. Na maioria dos casos, você deve gerar automaticamente os números sequenciais.

5. Na página **Parâmetros de varejo**, na guia **Códigos de barras**, selecione o código de barras criado anteriormente.
6. Na página **Parâmetros compartilhados de varejo**, na guia **Sequências numéricas**, selecione as sequências numéricas criadas para o número do cupom e a ID do código do cupom.
7. Agora você pode abrir a página **Cupons** e criar novos cupons.

## <a name="the-effect-of-partial-updates-on-coupons"></a>O efeito das atualizações parciais nos cupons

A funcionalidade de cupom abrange vários recursos distintos no Dynamics 365 para varejo. A sede do Microsoft Dynamics 365 para varejo (HQ) e o canal podem ser parcialmente atualizados em todos os componentes. Portanto, é importante que você entenda como as atualizações parciais afetam a funcionalidade do cupom como um todo.

- **A sede é atualizada parcialmente, mas o servidor de varejo e o PDV não serão atualizados.** Em uma atualização da sede, as páginas de cupom e desconto são atualizadas, e o mecanismo de preço de varejo também é atualizado. Se apenas um desses dois componentes for atualizado, algumas páginas do Retail não coincidirão com os dados de cálculo do preço. Portanto, cálculos de desconto inesperado ou erros inesperados podem ocorrer durante cálculos de desconto.
- **A sede é atualizada, mas o servidor de varejo e o PDV não serão atualizados (N-1).** Como nem todas as lojas de varejo podem ser atualizadas ao mesmo tempo, recomendamos que você atualize a sede antes de atualizar lojas de varejo. No cenário N-1, novas funcionalidades relacionadas a cupons não estarão disponíveis em lojas que ainda não tiverem sido atualizadas. Por exemplo, a funcionalidade do cupom apresenta linhas a serem "excluídas". Se você usar linhas de exclusão com desconto, elas não serão aplicadas em uma loja de varejo que esteja executando uma versão anterior.
- **A sede não é atualizada, mas o servidor de varejo e o PDV são atualizados (N+1).** Como o mecanismo de preço atualizado no servidor de varejo pode lidar com códigos de desconto convencionais durante os cálculos de preços, a atualização não deve ter impacto funcional nesse cenário.

