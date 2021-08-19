---
title: Criar opções de cobertura
description: As opções de cobertura no Microsoft Dynamics 365 Human Resources são níveis de cobertura para a eleição de um participante em um plano ou programa de benefícios.
author: andreabichsel
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 447317d0e9cb23bea21dae448048d05a3d989c89df17e4b8ea836201c20aefff
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741420"
---
# <a name="create-coverage-options"></a>Criar opções de cobertura

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

As opções de cobertura determinam quem deve receber a cobertura ou quanta cobertura está disponível em um plano de seguro. Por exemplo, em um plano médico, você pode ter uma opção **exclusivo para o funcionário**, uma opção **funcionário + 1** e uma opção **família**. No seguro de vida, você pode oferecer cobertura para **1 x salário** ou **2 x salário**.

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
   | **Status** | O status da opção de cobertura. Se o status da opção Cobertura estiver definido como Inativo, a opção Cobertura não poderá ser selecionada nos tipos de plano. |
   | **Porcentagem** | O valor percentual. Este campo estará ativo apenas se %x Salário tiver sido selecionado no campo Código de cobertura. |
   | **Divisor** | O divisor a ser usado no cálculo quando você seleciona o código de cobertura %x Salário. |
   | **Porcentagem mínima** | A porcentagem mínima quando você seleciona o código de cobertura Porcentagem. |
   | **Porcentagem máxima** | A porcentagem máximo quando você seleciona o código de cobertura Porcentagem. |

4. Em **Opções de qualificação para contato pessoal**, anexe a opção de qualificação para contato pessoal apropriada a cada opção de cobertura.

5. Em **Autoatendimento**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Permitir valor de contribuição do funcionário** | Especifica se os funcionários devem modificar o valor da contribuição no autoatendimento de benefícios quando selecionam benefícios. Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da contribuição que o empregado insere no autoatendimento de benefícios. |
   | **Permitir valor de cobertura do funcionário** | Especifica se os funcionários devem modificar o valor da cobertura no autoatendimento de benefícios quando selecionam benefícios. Se você marcar esta caixa de seleção, o sistema calculará os parâmetros do plano de benefícios com base no valor da cobertura que o empregado insere no autoatendimento para funcionários. |

6. Selecione **Salvar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
