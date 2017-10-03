---
title: "Configurar pré-requisitos para gerenciamento"
description: "Use este procedimento para habilitar processos de gerenciamento de não conformidade."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: e8f7ec305316b5290019ec28deed1cae382e93b3
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-prerequisites-for-management"></a>Configurar pré-requisitos para gerenciamento

[!include[task guide banner](../../includes/task-guide-banner.md)]

Use este procedimento para habilitar processos de gerenciamento de não conformidade. Uma não conformidade descreve um item ou um procedimento com um problema de qualidade, na qual as informações descritivas incluem a origem e o tipo do problema. Este procedimento usa a empresa de dados de demonstração USMF. Esse procedimento geralmente é realizado por um gerente de qualidade.


## <a name="enable-quality-management-processes-within-the-company"></a>Habilitar processos de gerenciamento de qualidade na empresa
1. Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.
2. Clique na guia gerenciamento de qualidade.
3. Selecione Sim no campo Usar gerenciamento de qualidade.
    * Selecione este parâmetro para habilitar processos de gerenciamento de qualidade para a empresa.  
4. No campo Preço por hora, digite um número.
    * Use o campo Preço por hora para inserir um preço de mão de obra por hora na moeda local. O preço por hora é usado para calcular o custo de operações relacionadas à não conformidade. O preço por hora e os custos calculados fornecem informações de referência para uma não conformidade e não interagem com outras funcionalidades.  
5. Clique em Configuração de relatório.
    * Esta página permite que você defina os tipos de nota de relatório de qualidade que serão usados em diferentes tipos de relatórios de gerenciamento de qualidade.  
6. Feche a página.
7. Feche a página.

## <a name="enable-user-for-nonconformance-processing"></a>Habilite o usuário para processar não conformidade
1. Vá para Administração do sistema > Usuários > Usuários.
    * Para processar a aprovação de uma não conformidade, o usuário que aprova ou rejeita as não conformidades deve ter um valor de “Nome“ atribuído na página Usuários. Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.  
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Nome com um valor de "Ricardo".
    * Use o filtro para localizar o usuário que aprovará ou rejeitará os registros de não conformidade.  
3. Na lista, clique no link na linha selecionada.
    * Para processar a aprovação de uma não conformidade, certifique-se de que o usuário que aprova ou rejeita as não conformidades tem um valor de “Nome“ atribuído na página Usuários.  
4. Clique em Opções do usuário.
5. Clique na guia Preferências.
6. Selecione Sim no campo Habilitar manuseio de documento.
    * Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.  
7. Feche a página.
8. Feche a página.
9. Feche a página.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Defina tipos de diagnóstico para o processamento de não conformidade
1. Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Tipos de diagnósticos.
    * Use a página Tipos de diagnóstico para definir uma classificação de ações de diagnóstico. Uma correção identifica o tipo de ação de diagnóstico que deve ser tomada em uma não conformidade aprovada, quem deve realizá-la e a data de solicitação e de conclusão planejada.  
2. Clique em Novo.
3. No campo Diagnóstico, digite um valor.
4. No campo Descrição, digite um valor.
5. Feche a página.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Defina encargos de qualidade para o processamento de não conformidade
1. Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Encargos de qualidade.
    * Use a página Encargos de qualidade para definir a classificação de encargos que serão usados em operações relacionadas a não conformidade.  
2. Clique em Novo.
3. No campo Código de encargo, digite um valor.
4. No campo Descrição, digite um valor.
5. Feche a página.

## <a name="define-the-operations-for-nonconformance-processing"></a>Defina as operações para o processamento de não conformidade
1. Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Operações.
    * Use a página Operações para definir uma classificação do trabalho que pode ser realizado para uma não conformidade aprovada. Quando você relaciona uma operação relacionada a uma não conformidade, você pode definir informações sobre o material associado, as horas de mão-de-obra e os encargos diversos necessários para executar a operação. Essas informações fornecem a base para calcular um custo estimado para executar a operação.  
2. Clique em Novo.
3. No campo Operação, digite um valor.
4. No campo Descrição, digite um valor.
5. Feche a página.

## <a name="define-problem-types-for-nonconformance-processing"></a>Defina tipos de problema para o processamento de não conformidade
1. Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Tipos de problemas.
    * Use a página Tipos de problema para definir uma classificação dos problemas de qualidade que são encontrados nos vários tipos de não conformidade. Os tipos de não conformidade incluem: Interno, Cliente, Fornecedor, Solicitação de serviço, Produção e Produção do coproduto. Um único tipo de problema pode ser associado aos vários tipos de não conformidade.  
2. Clique em Novo.
3. No campo Tipo de problema, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Tipos de não conformidade.
    * Use a página Tipos de não conformidade para autorizar o uso de um tipo de problema para um ou vários tipos de não conformidade. Por exemplo, um tipo de problema relacionado a um código de defeito pode ser aplicado a todos os tipos de não conformidade, enquanto um tipo de problema sobre reclamações do cliente só pode ser aplicado aos tipos de não conformidade de cliente e solicitação de serviço.  
6. Clique em Novo.
7. Na lista, marque a linha selecionada.
8. No campo Tipo de não conformidade, selecione uma opção.
9. Feche a página.
10. Feche a página.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Defina zonas de quarentena para o processamento de não conformidade
1. Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Zonas de quarentena.
2. Clique em Novo.
3. No campo Zona de quarentena, digite um valor.
4. No campo Descrição, digite um valor.
5. Feche a página.

