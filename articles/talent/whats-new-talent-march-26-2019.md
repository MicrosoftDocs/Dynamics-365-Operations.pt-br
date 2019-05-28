---
title: Novidades ou alterações no Dynamics 365 for Talent (26 de março de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-26
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 568a16a17ed3269c7b72f27f0d4b7bbdbd56630e
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517361"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-26-2019"></a>Novidades ou alterações no Dynamics 365 for Talent (26 de março de 2019)

[!include [banner](includes/banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="enhancements-to-interview-scheduling"></a>Aprimoramentos do agendamento de entrevista
Os seguintes aprimoramentos estão disponíveis no agendamento de entrevista.

- Os recrutadores ou gerentes de contratação agora podem enviar manualmente um lembrete para um entrevistador para que eles enviem seus comentários. O modelo de email associado para o lembrete também é configurável.
- Ao compartilhar o resumo da entrevista com o candidato, o agendador da entrevista pode optar por ocultar os nomes dos entrevistadores e também ocultar as linhas do resumo da entrevista.

## <a name="changes-in-onboard"></a>Alterações de Integração

### <a name="embedded-images-in-activities"></a>Imagens inseridas em atividades
Agora você pode inserir imagens diretamente nas atividades. Além de poder copiar e colar imagens da Web, você pode carregá-las do sistema de arquivos local. O tamanho da atividade é limitado a 1 MB. Se a imagem for muito grande, redimensione-a e tente carregá-la novamente.

[![Mapeamento](./media/embedimages.png)](./media/embedimages.png)

Esta versão inclui correções de bug menores para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
**Compilação 8.1.2210**

### <a name="custom-field-support-available-for-select-entities-in-common-data-service"></a>Suporte a campos de cliente disponível para determinadas entidades no Common Data Service 

Essas entidades do Common Data Service agora são compatíveis com campos de cliente criados no Dynamics 365 for Talent:

- Trabalhador
- Origem étnica
- Situação militar
- Código do idioma
- Cargo
- Tipo de trabalho
- Função de trabalho
- Cargo
- Tipo de posição
 
### <a name="employment-history-not-displayed-chronologically"></a>O histórico de empregos não era exibido de forma cronológica
Com essa alteração, a página do histórico de empregos agora exibe os registros de emprego de forma cronológica, independentemente da empresa. Você também pode as opções de classificação para classificar por empresa.

### <a name="fixed-compensation-plans-dont-appear-when-restricting-user-by-company-in-security"></a>Os planos de remuneração fixa não aparecem quando os usuários são restringidos por empresa em segurança.
Nesta versão, os planos de remuneração fixa agora aparecem quando os usuários são restringidos por empresa em segurança. Todas as configurações de segurança serão seguidas, e os planos de remuneração fixa aparecerão para as empresas cujos usuários tenham permissão de acesso. 

### <a name="cant-delete-job-records-using-open-in-excel-option-in-talent"></a>Não é possível excluir registros de trabalho usando-se a opção Abrir no Excel no Talent
Com essa versão, agora você pode remover os registros de trabalho usando a opção **Abrir no Excel** no Dynamics 365 for Talent.

### <a name="upgrade-to-common-data-service"></a>Fazer upgrade para o Common Data Service
Os prazos finais para atualizar para o Common Data Service se aproximam rapidamente. Entre na central de administração do PowerApps para determinar se sua base de dados precisa ser atualizada. Para obter mais informações sobre os prazos finais e as etapas necessárias para atualizar, consulte [Fazer upgrade para o Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>Em visualização

Para obter informações sobre como habilitar recursos de visualização, consulte [Acessar os recursos de visualização no Talent](./access-preview-feature.md).

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir que os códigos de motivo sejam especificados nos tipos de licença
As organizações podem precisar de informações adicionais relacionadas às solicitações de folga. Para obter essas informações, os funcionários precisam incluir um código de motivo em suas solicitações de folga. Com esta versão, você agora pode especificar os códigos de motivo associados a um dado tipo de licença e permitir que os funcionários selecionem um código de motivo em suas solicitações de folga.

### <a name="configure-reason-codes-to-be-required-when-submitting-time-off-for-certain-leave-types"></a>Configurar códigos de motivo a serem exigidos junto com o envio do pedido de folga para alguns tipos de licença
As organizações podem exigir códigos de motivo que devem ser definidos para tipos de licença específicos quando os funcionários enviam pedidos de folga. Isso pode ser exigido com base em requisitos regulatórios no país ou região do funcionário ou por uma política de empresa. Esta versão permite que o RH especifique os tipos de licença que exigem um código de motivo. Isso será reforçado quando os funcionários enviarem solicitações de folga cujo tipo de licença exija um código de motivo.

## <a name="coming-soon"></a>Em breve

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Segurança de compensação avançada (fixa e variável)
Em muitas organizações, gerentes de remuneração e benefícios só podem ter acesso a alguns tipos de registro de remuneração. Esses registros podem ser para funcionários executivos ou regionais. Com esta alteração, o RH pode gerenciar e manter os planos de remuneração para grupos de funcionários diferentes na organização. Você pode atribuir funções de segurança para planos fixos e variáveis que determinem o acesso a planos e dados de funcionário relacionados aos planos, como registros de bônus ou salário. Apenas as funções com permissão de acesso podem processar a remuneração para esses funcionários.

###  <a name="email-support-for-alerts"></a>Suporte de email para alertas
Com o Platform update 25, os usuários podem criar regras de alerta que enviam automaticamente notificações por email a contatos quando enviadas para um evento. 

### <a name="duplicate-employee-checks-user-interface-changes"></a>Verificações de funcionários duplicados: alterações da interface de usuário
Com esta alteração, as duplicatas são detectadas conforme você digita nos campos de nome, e um status exibe o número de duplicatas localizado. Você pode selecionar o link fornecido para abrir uma nova página a fim de avaliar se deve usar ou não a correspondência detectada. Para evitar a interrupção de entrada de dados, os formulários das duplicatas não são abertos automaticamente.
