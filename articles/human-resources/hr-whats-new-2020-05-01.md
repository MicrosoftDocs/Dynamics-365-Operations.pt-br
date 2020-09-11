---
title: Novidades ou alterações no Dynamics 365 Human Resources (1 de maio de 2020)
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 1º de maio de 2020.
author: Darinkramer
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 074c678d9d8294aabf4e78b2a6ee0fa53efbaf23
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712271"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (1 de maio de 2020)

Este artigo descreve os recursos novos ou alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3196. Os números entre parênteses em alguns títulos referem-se aos números de suporte do LCS para referência.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Novas entidades de gerenciamento de desempenho disponíveis na Estrutura de gerenciamento de dados (DMF)

As entidades a seguir agora estão disponíveis. Se você não vir essas entidades listadas na lista de entidades, use a opção **Atualizar entidades** em **Parâmetros de estrutura > Configurações de entidade > Atualizar lista de entidade**.

- **Competência de discussão**
- **Metas de discussão**
- **Medida de discussão**
- **Tópico de discussão**
- **Diário de desempenho**
- **Medição**
- **Medida de meta**

Além disso, a **Pontuação total** e a **Pontuação média** foram adicionadas à entidade **Discussão**.

## <a name="increase-length-of-leave-request-comments-275641"></a>Aumentar o tamanho de comentários da solicitação de licença (275641)

Os comentários sobre solicitações de licença agora permitem mais de 100 caracteres.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>Os comentários finais sobre as revisões não aparecem quando o gerente ou funcionário está conectado a uma empresa diferente (431688)

Todos os comentários aparecerão agora ao exibir revisões.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>Não há suporte para links definidos pelo usuário no formulário do novo trabalhador (390374)

Os links definidos pelo usuário são agora habilitados no formulário de **Trabalho simplificado**.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity causa falha na API OData (439476)

Essa alteração corrige a falha da API. Um nome duplicado tem este erro.

## <a name="in-preview"></a>Em visualização

## <a name="leave-suspension"></a>Sair da suspensão

Você pode suspender a licença e a ausência em Human Resources para um funcionário. Suspender licença interrompe a acumulação de licenças de licença para os tipos de licença selecionados. Se a suspensão ocorrer depois de um acúmulo ter sido processado, a suspensão da licença criará um ajuste rateado para o saldo de licença do funcionário. Para obter mais informações, consulte [Suspender licença](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Atualizar a experiência do usuário para indicar que a acumulação foi suspensa (429550)

Agora, a experiência do usuário indica que a acumulação foi suspensa para um plano.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Suspender a acumulação de licenças para tipos de licença especificados (272447)

Nesta versão, o HR pode criar uma regra para suspender as competências de licença para funcionários com solicitações de licença inseridas para licenças não pagas. A licença não remunerada pode ser um tipo, mas não precisa ser. Você pode suspender qualquer licença com base em outro tipo de licença.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Entidade DMF disponível para suspensões de acúmulos (429549)

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Adicionar código de motivo a suspensões de acúmulos (429547)

Os códigos de motivo foram adicionados à suspensão de acúmulos.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Iniciar transição dos parâmetros de Human Resources para os parâmetros de licença e ausência

Esta versão começa a combinar parâmetros de Human Resources com parâmetros de licença e ausência.

## <a name="carry-forward-rules"></a>Regras de postergação

Você pode especificar um tipo de licença postergada para saldos postergados nos quais ajustes postergados são transferidos. Por exemplo, se um funcionário adianta 10 dias, você pode escolher um tipo de licença diferente para esses 10 dias. Para obter mais informações, consulte [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Problemas conhecidos

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>A visualização do SharePoint não funcionará em alguns ambientes

Se a visualização de documentos armazenados no SharePoint não funcionar, tente o seguinte procedimento:

1. Verifique se a conta de usuário do administrador possui um email associado ao registro do usuário. Você pode exibir essas informações na página **Usuário**. Se o email não estiver configurado, você precisará adicionar o email e o provedor com o suplemento do OData Excel. Por padrão, o endereço de email não está presente no design do Excel. Será preciso editar o design do Excel, adicionar todos os campos, aplicar e atualizar. Depois de concluir essas etapas, você pode atualizar a conta de administrador.

2. Depois que a conta de administrador tiver uma conta de email associada, entre no Human Resources com credenciais de administrador.

3. Acesse um anexo no SharePoint para iniciar a visualização do documento.

4. Entre com outra conta de usuário que tenha acesso a anexos e verifique se a visualização funciona conforme o esperado.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)