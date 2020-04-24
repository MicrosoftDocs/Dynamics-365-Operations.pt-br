---
title: Configurar opções de qualificação para contato pessoal
description: Configure opções de qualificação para contatos pessoais no Microsoft Dynamics 365 Human Resources. Contatos pessoais podem ser beneficiários ou dependentes.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0275331e600770a9f38a33bc2c3170c4cf9be951
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229869"
---
# <a name="configure-personal-contact-eligibility-options"></a>Configurar opções de qualificação para contato pessoal

Este artigo mostra como configurar tipos de contatos pessoais para usar em benefícios no Microsoft Dynamics 365 Human Resources. Contatos pessoais podem ser beneficiários ou dependentes. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Opções de qualificação para contato pessoal**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Opção de qualificação** | Um nome ou código exclusivo da opção de qualificação para identificar a opção de qualificação. |
   | **Descrição** | Uma breve descrição da opção de qualificação. |
   | **Código de qualificação do contato** | O código do sistema que melhor descreve a opção de qualificação pessoal. As opções são: <ul><li>Relacionamento</li><li>Estudante</li><li>Dependente excedente</li><li>Dependente incapaz maior de idade</li></ul> |
   | **Status** | O status da opção de qualificação. Se o status de uma opção de qualificação estiver definido como inativo, você não poderá selecionar essa opção de qualificação de contato pessoal para contatos pessoais. |
   | **Relacionamento** | Especifica o relacionamento entre o contato pessoal e o funcionário. Esse campo estará ativo apenas se o código de qualificação do contato estiver definido como Relacionamento. |
   | **Classificar por vencimento** | A idade máxima de um contato pessoal qualificado para o plano de benefícios. Esse campo estará ativo apenas se você selecionar um relacionamento. Essa idade é comparada com a idade calculada do contato pessoal. A idade calculada é: (data de cobertura – data de nascimento do contato pessoal/365). Esse número é sempre um inteiro. |

4. Selecione **Salvar**. 
