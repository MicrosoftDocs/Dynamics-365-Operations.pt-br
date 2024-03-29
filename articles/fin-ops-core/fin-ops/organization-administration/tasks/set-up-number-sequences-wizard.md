---
title: Configurar sequências numéricas usando um assistente
description: Este artigo explica como configurar todas as sequências numéricas necessárias ao mesmo tempo usando um assistente.
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cae739aad1166eee1abebe3c0adc7939bca55bc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847053"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>​Configurar sequências numéricas usando um assistente​

[!include [banner](../../includes/banner.md)]

Sequências numéricas são usadas para gerar identificadores exclusivos e legíveis para registros de dados mestres e registros de transações que os exigirem. Um registro de transação ou de dados mestres que exige um identificador é conhecido como referência. Antes de criar novos registros para referência, é necessário configurar uma sequência numérica e associá-la à referência. Este artigo explica como configurar todas as sequências numéricas necessárias ao mesmo tempo usando um assistente. A empresa de dados demo usada para criar este procedimento é USMF.

1. Acesse **Navegação > Módulos > Administração da organização > Sequências numéricas > Sequências numéricas**.
2. Selecione **Gerar**.
3. Selecione **Avançar**.

   - Nessa página, é possível alterar o código de identificação, o valor mais baixo e o valor mais alto. Além disso, é possível indicar se a sequência numérica deverá ser contínua.   
   - Não selecione a opção **Contínuo** se for necessário alocar antecipadamente os números para a sequência numérica. Para adicionar um segmento de escopo ao formato de uma sequência numérica, selecione o formato na lista, e então selecione **Incluir escopo ao formato**. Para remover um segmento de escopo do formato de uma sequência numérica, selecione o formato na lista, e então selecione **Remover escopo do formato**. Para excluir uma sequência numérica da geração automática, selecione a sequência numérica na lista, e então selecione **Excluir**.  

4. Selecione **Avançar**.
5. Selecione **Concluir**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
