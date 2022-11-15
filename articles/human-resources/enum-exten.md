---
title: Extensibilidade de enumeração de base de gênero
description: Este artigo fornece uma visão geral da extensibilidade da enumeração base de gênero (enum).
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749307"
---
# <a name="gender-base-enum-extensibility"></a>Extensibilidade de enumeração de base de gênero

A enumeração (enum) **Gênero** agora não é extensível. Este artigo descreve as alterações que você deve fazer na base de código se você pretende estender a enumeração **Gênero**.

## <a name="gender-vs-hcmpersongender"></a>Gênero vs. HcmPersonGender

Há duas enumerações para valores de gênero:

- **Gênero** (Plataforma de Aplicativos)
- **HcmPersonGender** (PersonnelManagement)

A enumeração **Gênero** é usada em todo o Microsoft Dynamics 365 Finance, enquanto a **HcmPersonGender** é específica para a funcionalidade de gerenciamento de capital humano (HCM). Se você estiver usando a funcionalidade HCM e fizer alterações na enumeração **Gênero**, faça as mesmas alterações em **HcmPersonGender**. Por exemplo, se você adicionar **Transgender** à enumeração **Gênero**, adicione **Transgender** à enumeração **HcmPersonGender** também.

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (Classe)

Uma nova classe **HcmPersonGenderTranformUtil** foi criada para permitir a tradução entre os dois enumeradores básicos. Nessa classe, há dois métodos: **convertGenderToHcmPersonGender** e **convertHcmPersonGenderToGender**. Você deve criar uma extensão usando a classe **Cadeia de Comando** ou **manipuladores de evento** e estender os dois métodos para mapear novos valores que são adicionados ao enumerador de base.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (Classe)

**PayrollStateWageTaxPrepDP** é a classe do provedor de dados do relatório SQL Server Reporting Services (SSRS) de **Prep. Imposto do Salário de Estado da Folha de Pagamento**. Nos Estados Unidos, três valores estão disponíveis: **Masculino**, **Feminino** e **Não especificado**. No método **populatePayrollStateWageTaxPrepTmp**, há uma instrução switch usada para mapear o valor da enumeração **HcmPersonGender** para um desses três campos: **IsMale**, **IsFemale** ou **IsUnspecifiedGender**. O valor padrão para a instrução switch é **IsUnspecifiedGender**. Se adicionar qualquer valor à enumeração **HcmPersonGender** para mapear de maneira diferente, você deve criar uma extensão usando a classe **Cadeia de Comando** no método **populatePayrollStateWageTaxPrepTmp** para alterar o valor, conforme necessário.

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (Classe)

A integração **smmOutlookSync_Contact** vincula valores de e para **Outlook** e **Pessoas de contato**. O **Outlook** oferece suporte a três valores: **Masculino**, **Feminino** e **Não especificado**. A classe tem dois métodos para ajudar a mapear **Gêneros** para **OutlookGenders**. O método padrão é **NonSpecific/UnSpecified**. Se criar valores adicionais para a enumeração **Gender**, você deve criar uma extensão usando a classe **Cadeia de Comandos** nos dois métodos, e mapear, conforme necessário.
