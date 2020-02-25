---
title: Novidades ou alterações no Dynamics 365 Talent (23 de julho de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2019
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
ms.search.validFrom: 2019-07-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8d89b1251429281521f32338f642cc7034420e0b
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3005977"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-23-2019"></a>Novidades ou alterações no Dynamics 365 Talent (23 de julho de 2019)

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Alterações no Attract

### <a name="pdf-renderer-for-candidate-documents"></a>Renderizador de PDF para documentos do candidato

Os usuários do Attract agora pode visualizar anexos em PDF para candidatos no visualizador de documentos em vez de baixar os anexos.

### <a name="signing-up-for-attract-user-research-group"></a>Inscrição no grupo de pesquisa de usuários do Attract 

Ao planejar novos recursos de produtos ou enviar recursos de visualização, procuramos nossos usuários para ajudar a orientar nossa direção. Os usuários interessados agora ​​podem se inscrever para fazer parte do nosso grupo de pesquisa de usuários por meio do link de inscrição em nosso aplicativo.

### <a name="job-approvals-appear-on-the-home-page"></a>As aprovações de trabalho aparecem na página inicial

As aprovações aparecem em uma seção **Aprovações** no painel. Os aprovadores podem revisar suas aprovações em **Atribuída(s) a você**, que mostra a ID do trabalho, o cargo, outros aprovadores e a data em que o trabalho foi atribuído. Os usuários que enviam um trabalho para aprovação podem revisar seus trabalhos em **Solicitado por você**, que mostra os aprovadores que ainda precisam aprovar o trabalho enviado.

## <a name="changes-in-onboard"></a>Alterações de Integração
Esta versão inclui correções de bug menores para o Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Alterações no Core HR
As alterações descritas nesta seção aplicam-se ao número da compilação 8.1.2394.

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>A entidade oferece suporte a campos personalizados no Common Data Service 

Com esta versão, o **Calendário de trabalho** e o dia do **Calendário de trabalho** agora oferecem suporte a campos personalizados Common Data Service.

### <a name="restrict-leave-types-in-time-off-requests"></a>Restringir os tipos de licença em solicitações de folga

As organizações podem oferecer muitos tipos diferentes de licenças aos funcionários. Entretanto, talvez não seja apropriado para os funcionários enviar solicitações de folga para alguns tipos de licença. Esses tipos de licença podem ser gerenciadas pelo RH. Nessa versão, você pode configurar para que tipos de licença os funcionários podem enviar solicitações de folga. 

## <a name="in-preview"></a>Em visualização

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Os recursos de visualização estão habilitados somente em instâncias da área restrita

Quando você provisiona uma nova instância do Talent, pode especificar se o tipo de instância é **Produção** ou **Área restrita**. As instâncias do tipo **Área restrita** permitem testes antecipados de novos recursos. Todas as instâncias do Talent existentes serão atualizadas para o tipo de instância de **Produção**. Se desejar que uma de suas instâncias existentes sejam atualizadas para o tipo de instância **Área restrita**, fale com o [Suporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar a solicitação de alteração.

Para obter mais informações sobre como as alterações são publicadas, consulte [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Exiba informações estendidas de desempenho no autoatendimento de gerente

Uma nova opção permitirá que gerentes exibam o desempenho de seus relatórios diretos e de seus relatórios estendidos. Atualmente, os gerentes de linha podem atribuir e atualizar metas de desempenho e emitir novas revisões, que são cogeridas pelos funcionários. Além disso, os gerentes diretos e seus funcionários podem manter e atualizar diários de desempenho para ajudar a garantir que o processo de avaliação de desempenho corra bem. Quando essa alteração for implementada, gerentes poderão exibir e manter informações de desempenho para seus relatórios estendidos além de seus relatórios diretos. 

## <a name="coming-soon"></a>Em breve

### <a name="region-support-for-canada-and-southeast-asia"></a>Suporte regional ao Canadá e ao sudeste da Ásia

Temos o prazer de anunciar que as regiões do Canadá e do sudeste da Ásia estarão disponíveis para o Talent em 1º de agosto de 2019. Com essa alteração, você pode criar ambientes nas regiões do Canadá e da Ásia, e todos os dados do Talent serão mantidos apenas dentro desses locais. Você pode criar um ambiente nessas novas regiões selecionando o local na caixa de diálogo Novo ambiente e usar esse ambiente para provisionar o Talent no LCS conforme descrito aqui [Provisionar o Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

Não há suporte para a migração de dados de projetos existentes de outras regiões para as regiões canadense e asiática. Somente os novos projetos podem ser provisionados a essas novas regiões com suporte.
