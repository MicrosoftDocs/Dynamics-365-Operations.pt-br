---
title: Configurar pré-requisitos do gerenciamento de não conformidade
description: Use este tópico para habilitar processos de gerenciamento de não conformidade.
author: perlynne
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventParameters, InventTestReportSetup, SysUserManagement, SysUserSetup, InventTestDiagnosticType, InventTestMiscCharges, InventTestOperation, InventProblemType, InventProblemTypeSetup, InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8c4de822dcda604241416165a961e4b0bacaeb5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422440"
---
# <a name="set-up-prerequisites-for-nonconformance-management"></a>Configurar pré-requisitos do gerenciamento de não conformidade

[!include [banner](../../includes/banner.md)]

Use este tópico para habilitar processos de gerenciamento de não conformidade. Uma não conformidade descreve um item ou um procedimento com um problema de qualidade, na qual as informações descritivas incluem a origem e o tipo do problema. Este procedimento usa a empresa de dados de demonstração USMF. Esse procedimento geralmente é realizado por um gerente de qualidade.


## <a name="enable-quality-management-processes-within-the-company"></a>Habilitar processos de gerenciamento de qualidade na empresa
1. No Painel de Navegação, vá para **Painel de navegação > Módulos > Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque**.
2. Selecione a guia **Gerenciamento de qualidade**.
3. Selecione **Sim** no campo **Usar gestão de qualidade** para habilitar processos de gerenciamento de qualidade para a empresa.
4. No campo **Preço por hora**, insira um número na moeda local. O preço por hora é usado para calcular o custo de operações relacionadas à não conformidade. O preço por hora e os custos calculados fornecem informações de referência para uma não conformidade e não interagem com outras funcionalidades.  
5. Selecione **Configuração de relatório** para definir os tipos de nota de relatório de qualidade que serão usados em diferentes tipos de relatórios de gerenciamento de qualidade.

## <a name="enable-user-for-nonconformance-processing"></a>Habilite o usuário para processar não conformidade
1. No painel de navegação, vá para **Módulos > Administração do sistema > Usuários > Usuários**. 
2. Use o Filtro Rápido para localizar o usuário que aprovará ou rejeitará os registros de não conformidade. Por exemplo, filtre o campo **Nome** com um valor de `Ricardo`. Para processar a aprovação de uma não conformidade, o usuário que aprova ou rejeita não conformidades precisa possuir um valor "Nome" atribuído na página **Usuários**. Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.  
3. Marque a linha de registro desejada.
4. Selecione **Opções de usuário**.
5. Selecione a guia **Preferências**.
6. Selecione **Sim** no campo **Habilitar manuseio de documento**.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Defina tipos de diagnóstico para o processamento de não conformidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Tipos de diagnóstico**. Use a página **Tipos de diagnóstico** para definir uma classificação de ações de diagnóstico. Uma correção identifica o tipo de ação de diagnóstico que deve ser tomada em uma não conformidade aprovada, quem deve realizá-la e a data de solicitação e de conclusão planejada.  
2. Selecione **Novo**.
3. No campo **Diagnóstico**, digite um valor.
4. No campo **Descrição**, digite um valor.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Defina encargos de qualidade para o processamento de não conformidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Encargos de qualidade**. Use a página **Encargos de qualidade** para definir a classificação de encargos que serão usados em operações relacionadas a não conformidade.  
2. Selecione **Novo**.
3. No campo **Código de encargo**, digite um valor.
4. No campo **Descrição**, digite um valor.

## <a name="define-the-operations-for-nonconformance-processing"></a>Defina as operações para o processamento de não conformidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Operações**. Use a página **Operações** para definir uma classificação do trabalho que pode ser realizado para uma não conformidade aprovada. Quando você relaciona uma operação relacionada a uma não conformidade, você pode definir informações sobre o material associado, as horas de mão-de-obra e os encargos diversos necessários para executar a operação. Essas informações fornecem a base para calcular um custo estimado para executar a operação.  
2. Selecione **Novo**.
3. No campo **Operação**, digite um valor.
4. No campo **Descrição**, digite um valor.

## <a name="define-problem-types-for-nonconformance-processing"></a>Defina tipos de problema para o processamento de não conformidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Tipos de problemas**. Use a página **Tipos de problema** para definir uma classificação dos problemas de qualidade que são encontrados nos vários tipos de não conformidade. Os tipos de não conformidade incluem: **Interno**, **Cliente**, **Fornecedor**, **Solicitação de serviço**, **Produção** e **Produção do coproduto**. Um único tipo de problema pode ser associado aos vários tipos de não conformidade.  
2. Selecione **Novo**.
3. No campo **Tipo de problema**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. Selecione **Tipos de não conformidade**. Use a página **Tipos de não conformidade** para autorizar o uso de um tipo de problema para um ou vários tipos de não conformidade. Por exemplo, um tipo de problema relacionado a um código de defeito pode ser aplicado a todos os tipos de não conformidade, enquanto um tipo de problema sobre reclamações do cliente só pode ser aplicado aos tipos de não conformidade de cliente e solicitação de serviço.  
6. Selecione **Novo**.
7. No campo **Tipo de não conformidade** da nova linha, selecione uma opção.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Defina zonas de quarentena para o processamento de não conformidade
1. No painel de navegação, vá para **Módulos > Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Zonas de quarentena**.
2. Selecione **Novo**.
3. No campo **Zona de quarentena**, digite um valor.
4. No campo **Descrição**, digite um valor.
5. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]