---
title: Propor aquisições de ativo fixo
description: Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos.
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd54642e5ec6c56fbc3a5ebb07fc8fdaf5545926
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725670"
---
# <a name="propose-fixed-asset-acquisitions"></a>Propor aquisições de ativo fixo

[!include [banner](../../includes/banner.md)]

Este tópico descreve como adquirir um ativo fixo usando a proposta de aquisição no Diário de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF. Para adquirir um ativo fixo por meio de um diário de propostas de ativos fixos, é necessário criar o registro de ativo fixo e definir o preço de aquisição no registro de ativos.

## <a name="create-an-asset-acquisition-proposal"></a>Crie uma proposta de aquisição de ativo

Conclua estas etapas para criar uma proposta de aquisição de ativo. 

1. No Painel de navegação, Acesse **Módulos > Ativos fixos > Entradas de diário > Diário de ativos fixos**.
2. Selecione **Novo**.
3. No campo **Nome**, insira ou selecione um valor.
4. No Painel de Ações, selecione **Linhas**.
5. Selecione **Propostas**.
6. Selecione **Proposta de aquisição**.
7. Selecione **Filtro**. Selecione **Redefinir** para limpar valores anteriores.
8. Selecione a linha de **Número de ativo fixo**.
9. No campo **Critérios**, insira ou selecione um valor. Defina os critérios restantes para os ativos fixos que você deseja adquirir com esta proposta.  
10. Selecione **OK** duas vezes a sair do painel.
- Verifique se as linhas de transação foram criadas.  
- Somente os ativos fixos com a data de aquisição e o preço de aquisição definidos no registro serão incluídos na proposta de aquisição.  
11. Na página, selecione a guia **Registros**.
12. Selecione **Lançar**.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Inclua dimensões financeiras padrão em uma proposta de aquisição

A transação de aquisição pode ser criada usando suplementos do Excel, acessando **Ativos fixos > Entradas de diário > Diário de ativos fixos**. Crie um novo diário e mova-o para a seção **Linhas** da página e selecione o ícone do Excel. Depois, selecione uma linha de Diário de ativos fixos. O sistema criará e abrirá um modelo do Excel representando linhas do diário. Você pode adicionar dados nas linhas do diário que está adicionando no modelo e publicar essas informações de volta no sistema. 

Se as dimensões padrão foram configuradas para o registro de ativos selecionado e os ativos fixos correspondentes inseridos no modelo do Excel, as dimensões financeiras padrão serão retiradas a partir dos dados mestres de registros de ativos quando o diário for lançado do Excel para o sistema. Para incluir dimensões financeiras em um registro de ativos automaticamente ao mesmo tempo em que lança o diário de ativos fixos a partir do suplemento do Excel, as dimensões padrão devem ser configuradas com antecedência.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
