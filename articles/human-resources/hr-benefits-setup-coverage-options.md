---
title: Criar opções de cobertura
description: Este artigo descreve as opções de cobertura no Microsoft Dynamics 365 Human Resources para eleição de um participante em um plano ou programa de benefícios.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8569cabf72871396b9935a14a5637e5e645705fb
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848213"
---
# <a name="create-coverage-options"></a>Criar opções de cobertura


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

As opções de cobertura determinam quem deve receber a cobertura ou quanta cobertura está disponível em um plano de seguro. Por exemplo, em um plano médico, você pode ter uma opção **Exclusivo para o funcionário**, uma opção **Funcionário + 1** e uma opção **Família**. No seguro de vida, você pode oferecer cobertura para **1 x salário** ou **2 x salário**.

Depois que as opções de cobertura de benefícios são definidas, você pode reutilizá-las. Você pode associar uma opção a um ou mais planos.

> [!IMPORTANT]
> Depois de definir as opções de cobertura, anexe-as a um tipo de plano de benefícios. O tipo de plano é então associado a um plano ou programa de benefícios. As opções de cobertura associadas a um tipo de plano estão disponíveis para todos os planos desse tipo que são criados.

## <a name="create-coverage-options"></a>Criar opções de cobertura
1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Opções de cobertura**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Opção de cobertura** | Um nome de opção de cobertura exclusivo. |
   | **Descrição** | Uma descrição da opção de cobertura. |
   | **Código de cobertura** | Os códigos de cobertura atribuem valores mínimos e máximos para cada tipo de pessoa coberta elegível. Um código de cobertura indica quem está coberto ou o valor da cobertura permitida para um tipo de plano. É possível expressar o valor da cobertura como um valor em dólar ou uma porcentagem. Por exemplo:<ul><li>**Emp+1** – para ser qualificado, o funcionário deve ter um dependente selecionado (se mais de um for selecionado, a qualificação não será possível).</li><li>**Emp+family** – para ser qualificado, o funcionário deve ter pelo menos dois dependentes selecionados.</li></ul> |
   | **Número máximo** | O número máximo de dependentes. |
   | **Status** | O status da opção de cobertura. Se o status da opção Cobertura estiver definido **Inativo**, a opção Cobertura não pode ser selecionada nos tipos de planos. |
   | **Porcentagem** | O valor percentual. Este campo estará ativo apenas se %x Salário tiver sido selecionado no campo Código de cobertura. |
   | **Divisor** | O divisor a ser usado no cálculo quando você seleciona o código de cobertura %x Salário. |
   | **Porcentagem mínima** | A porcentagem mínima quando você seleciona o código de cobertura Porcentagem. |
   | **Porcentagem máxima** | A porcentagem máximo quando você seleciona o código de cobertura Porcentagem. |

4. Em **Opções de qualificação para contato pessoal**, anexe a opção de qualificação para contato pessoal apropriada a cada opção de cobertura.

5. Em **Autoatendimento**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Permitir valor de contribuição do funcionário** | Especifica se os funcionários devem modificar o valor da contribuição no autoatendimento de Benefícios quando selecionam benefícios. Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da contribuição que o empregado insere no autoatendimento de Benefícios. |
   | **Permitir valor de cobertura do funcionário** | Especifica se os funcionários devem modificar o valor da cobertura no autoatendimento de Benefícios quando selecionam benefícios. Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da cobertura que o empregado insere no autoatendimento para funcionários. |

6. Selecione **Salvar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
