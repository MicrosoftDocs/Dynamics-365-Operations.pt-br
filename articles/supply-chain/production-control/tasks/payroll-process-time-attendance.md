---
title: Habilitar o processo de folha de pagamento para horário e presença
description: Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5805cc31bf9c7c2231defab63dc9a1e67f82622a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206947"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Habilitar o processo de folha de pagamento para horário e presença

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como habilitar o processo de folha de pagamento de tempo e presença. A empresa de dados demo usada para criar este procedimento é USMF.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Criar um tipo de pagamento com uma taxa de pagamento relacionada
1. Hora e atendimento > Configuração > Folha de pagamento > Tipos de pagamento
2. Clique em Novo.
3. No campo Tipo de pagamento, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Salvar.
6. Clique em Taxas.
    * As taxas para os tipos de pagamento são definidas para intervalos de tempo específicos e taxas individuais podem ser criadas para trabalhadores. Nem sempre é necessário criar taxas para tipos de pagamento em tempo e presença. Essas informações já podem existir no sistema de folha de pagamento usado na geração dos salários.  
7. Clique em Novo.
8. Na lista, marque a linha selecionada.
9. No campo Taxa, insira um número.
10. Clique em Salvar.

## <a name="create-a-pay-agreement"></a>Criar um contrato de pagamento
1. Feche a página.
2. Feche a página.
3. Vá para Contratos de pagamento.
    * Hora e atendimento > Configuração > Contratos de pagamento  
4. Clique em Novo.
5. No campo Contrato de pagamento, digite um valor.
6. No campo Descrição, digite um valor.
7. Clique em Salvar.
8. Clique em Linhas de contrato.
9. Clique em Novo.
10. Na lista, marque a linha selecionada.
11. No campo Tipo de perfil, insira ou selecione um valor.
12. No campo Tipo de pagamento, insira ou selecione um valor.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Configurar o contrato de pagamento do funcionário por tempo e registro
1. Feche a página.
2. Feche a página.
3. Vá para Trabalhadores de registro de tempo.
    * Hora e atendimento > Configuração > Tempo de registro dos trabalhadores  
4. Na lista, clique no link na linha selecionada.
5. Clique na guia Emprego.
6. Expanda a seção de Tempo de registro.
7. Clique em Editar.
8. No campo Contrato de pagamento, insira ou selecione um valor.

