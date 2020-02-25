---
title: Definir regras e políticas de qualificação para o benefício
description: O artigo mostra como é possível criar regras e políticas de qualificação para o benefício e atribuir regras a benefícios.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: fa507591fc89eaebf617deedb15b15a0f93f971d
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008159"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>Definir regras e políticas de qualificação para o benefício

O artigo mostra como é possível criar regras e políticas de qualificação para o benefício e atribuir regras a benefícios.  

A empresa de dados demo usada para criar este registro é USMF.


## <a name="create-benefit-eligibility-policy-rule-type"></a>Crie tipos de regras de política de qualificação para benefícios
1. Vá para Recursos humanos > Benefícios > Qualificação > Tipos de regras de política de qualificação para o benefício.
2. Clique em Novo.
3. No campo Nome da regra, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Nome da consulta, clique no botão suspenso para abrir a pesquisa.
6. Na lista, clique no link na linha selecionada.
7. Clique em Salvar.
8. Feche a página.

## <a name="benefit-eligibility-policy"></a>Política de qualificação para o benefício
1. Vá para Recursos humanos > Benefícios > Qualificação > Políticas de qualificação para o benefício.
2. Selecione uma diretiva existente de benefício.
3. Na lista, clique no link na linha selecionada.
4. Ative/desative a expansão das seções de Organizações de política.  Aqui você pode adicionar ou remover todas as organizações que você deseja incluir na diretiva.
5. Expanda ou recolha a seção de regras de diretivas.
6. Na lista, localize a regra de política criada previamente.
7. Clique em Criar regra de política.
8. No campo Data efetiva, insira a data na qual a diretiva entre em vigor.
    * Definir datas efetivas e finais permite que você faça as alterações futuras às regras de diretiva e remove a necessidade de voltar à diretiva quando desejar que essas alterações sejam aplicadas.  
9. 
    * Por exemplo se você quis que a regra se aplicasse somente aos Gerentes de vendas, você pode criar a Cláusula onde dizendo: Onde a descrição de posição é igual ao Gerente de vendas.  Você pode E ou Ou multiplicar Onde declarações juntas na regra.  
10. Clique em OK.
11. Feche a página.
12. Feche a página.

## <a name="assign-rule-to-benefit"></a>Atribuir regra ao benefício
1. Ir para Recursos humanos > Benefícios > Benefícios.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. Expanda ou recolha a seção de qualificação de diretivas.
5. Clique em Editar.
6. No campo Qualificação, selecione a Regra baseada na lista.
7. No campo Tipo de regra, clique no botão suspenso para abrir a pesquisa.
8. Na lista, localize e selecione a regra que você criou anteriormente.
9. Na lista, clique no link na linha selecionada.
10. Clique em Salvar.
11. Feche o formulário.

