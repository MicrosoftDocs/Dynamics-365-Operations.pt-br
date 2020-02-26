---
title: Gerenciar recursos
description: Saiba como habilitar ou desabilitar novos recursos no Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84ff11e8237ce0669f7f6ac70c5b4411c5d4b466
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008061"
---
# <a name="manage-features"></a>Gerenciar recursos

Como parte de liberação contínua de novas funcionalidades do Microsoft Dynamics 365 Human Resources, queremos que nossos clientes aproveitem novos recursos o mais rápido possível. Fornecemos recursos de visualização, que estão quase prontos para disponibilidade geral e passam por um teste extenso. Estamos procurando apenas um círculo final de comentários de cliente e validação antes de liberá-los para disponibilidade geral.

Para obter mais informações sobre novos recursos no Human Resources, consulte [Novidades em Human Resources](hr-admin-whats-new.md) e [Dynamics 365 e Plano de versão do Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1).

O espaço de trabalho **Gerenciamento de recursos** fornece uma lista de recursos entregues em cada versão. Por padrão, os novos recurso estão desativados. Você pode usar o espaço de trabalho para ativá-los e exibir a documentação deles. Para obter mais informações sobre o Gerenciamento de recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho **Gerenciamento de recursos**, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.

Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho **Gerenciamento de recursos** indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

## <a name="enable-or-disable-preview-features"></a>Habilitar ou desabilitar recursos de visualização

Para acessar os recursos de visualização, primeiro é preciso ativá-los no ambiente. A habilitação ou desabilitação de recursos de visualização é específica do ambiente.

> [!IMPORTANT]
> Os recursos da versão prévia estão disponíveis somente em ambientes de **Área restrita**. Quando você ativa um recurso de visualização, você os habilita para todos os usuários da organização que estão no ambiente. Ao desativar o recurso de visualização, você o desabilita e o torna inacessível a seus usuários. Os recursos de visualização limitaram o suporte em Human Resources. Eles podem usar menos medidas de privacidade e segurança, e elas não estão incluídas no contrato de nível de serviço (SLA) de Human Resources. Você não deve usar recursos de visualização para processar dados pessoais (isso é, quaisquer informações que podem identificar você), ou para processar outros dados que estão sujeitos a requisitos de conformidade regulatório.

1. No Human Resources, selecione **Administração do sistema**.

2. Selecione o bloco **Gerenciamento de recursos**.

3. Para habilitar um recurso de visualização, selecione-o na lista e, em seguida, selecione **Habilitar**. Para desabilitar um recurso de visualização, selecione-o na lista e, em seguida, selecione **Desabilitar**.

## <a name="preview-feature-benefits-management"></a>Recurso de visualização: Gerenciamento de benefícios

O gerenciamento de benefícios oferece uma solução flexível que oferece suporte a uma ampla variedade de opções de benefícios, juntamente com uma experiência de funcionário fácil de usar que apresenta suas ofertas. Para obter mais informações sobre a configuração e o uso do gerenciamento de benefícios, consulte [Visão geral do Gerenciamento de benefícios](hr-benefits-management-overview.md).

O gerenciamento de benefícios substitui a funcionalidade do espaço de trabalho de **Benefícios**. Ao habilitar o recurso de visualização de gerenciamento de benefícios, não será mais possível acessar os seguintes formulários no espaço de trabalho **Benefícios**:

- **Benefícios**
- **Elementos do benefício**
- **Taxas de cálculo de contribuição**
- **Resultados da inscrição no benefício**
- **Resultados da expiração e da extensão de benefícios**
- **Tipos de regras de política de qualificação para o benefício**
- **Políticas de qualificação para benefícios**
- **Eventos de qualificação**

Você pode exibir as informações desses formulários no modo somente leitura. Se desejar editar as informações, você deve primeiro desabilitar o recurso de visualização de gerenciamento de benefícios.

### <a name="benefits-management-known-issues"></a>Problemas conhecidos do gerenciamento de benefícios

#### <a name="life-events"></a>Eventos de vida

Ao processar eventos de vida, o usuário receberá uma mensagem de erro:

A data inicial da cobertura deve estar entre o *início do período de plano* e *final do período de plano*. 

O evento de vida continuará a ser processado conforme o esperado.

#### <a name="eligibility-processing"></a>Processando qualificação

Ao executar a qualificação para benefícios que usam um salário 1-5X, % de salário e valor de cobertura de valor simples, a data de detalhes do benefício deve ser definida como a data de início do funcionário no **Histórico de emprego**, com horas trabalhadas, frequência de pagamento e valor de salário de benefícios anuais. Se houver remuneração fixa para o funcionário, insira as horas trabalhadas juntamente com a frequência de pagamento e o valor do salário anual será calculado. Se o funcionário for assalariado, as horas trabalhadas não serão necessárias. Recomendamos que, ao criar novos trabalhadores, insira a remuneração fixa primeiro. Para atualizar o registro de detalhes de benefícios: navegue até o **Trabalhador > Histórico do trabalhador > Detalhes do emprego**. Ajuste a data para a data de início dos trabalhadores.

#### <a name="employee-self-service"></a>Autoatendimento para funcionários

Os funcionários podem selecionar um plano para o qual não são qualificados e fazer check-out. Por exemplo: um trabalhador não tem nenhum dependente, mas tem permissão para selecionar um plano médico com uma opção de cobertura familiar.

O valor do funcionário não é calculado ao atualizar o valor da cobertura do seguro de vida útil. Por exemplo, quando um funcionário é oferecido a um plano de seguro de vida, ele pode selecionar até US$ 50.000 em cobertura a um custo de US$ 0,36 por US$ 1.000 de cobertura.  Quando o funcionário atualiza o valor da cobertura, o custo associado do funcionário permanece em zero.

Para um plano de benefício que permita somente uma única seleção desse tipo de plano, o usuário receberá um erro, caso tente renunciar a um plano depois de selecionar um plano. Por exemplo, um usuário seleciona um plano médico e o coloca em seu carrinho. O usuário seleciona **Renunciar** a outro plano médico. O usuário receberá uma mensagem de erro.

## <a name="preview-features-in-leave-and-absence"></a>Visualizar recursos na licença e ausência

Visualizar recursos na licença e ausência inclui:

- **Calendário de licenças e ausências da empresa** - Os parâmetros de licença e ausência moverão de **Parâmetros de recursos humanos** a uma nova tela chamada **Parâmetros de licença e ausência**. A nova tela inclui uma nova guia **Calendário**. Esta visualização habilita apenas um subconjunto dos parâmetros. Você pode acessar a nova tela na guia **Links** do espaço de trabalho **Licença e ausência**. Os calendários incluem:
  - **Calendário da empresa** - mostra todas as solicitações de tempo limite do funcionário. As pessoas com a função **Human resources** podem acessar este calendário na guia **Links** da área de trabalho **Licença e ausência**.
  - **Calendário da equipe do gerente** - mostra todas as solicitações de tempo limite dos relatórios diretos. Os gerentes podem acessar o calendário da guia **Minha equipe** no auto-atendimento para funcionários em **Licença e ausência**. 

- **Calendários de férias e ausências** - Os tipos de licença incluem uma nova opção de **Feriado**, usada em conjunto com o calendário de horário de trabalho. Os dias definidos por feriados e recessos agora são designados como **Feriado** quando os dias de trabalho são gerados. Quando as competências são processadas, os ajustes são feitos aos funcionários atribuídos ao calendário para contabilizar os feriados que ocorrem em um dia útil.

- **Manter auditoria de acumulação** - Uma nova tela permite que você examine quando as competências foram processadas e excluídas, ambas por funcionários e funcionários individuais. Você pode acessar essa nova tela na guia **Links** do espaço de trabalho **Licença e ausência**.

- **Manter exclusão da competência** - Você pode excluir registros de competência para planos de licença específicos. Você pode acessar essa nova opção na guia **Links** do espaço de trabalho **Licença e ausência**. Para funcionários individuais, esta opção aparece no agrupamento de **Licenças e ausências** no perfil do funcionário. 

- **Arredondamento de acúmulos de licença** - Novas opções para **Tipo de licença** definem qual tipo de arredondamento de acúmulos deve ser usado, mais a precisão decimal do arredondamento durante o processo de acumulação. Quando as competências são processadas, o arredondamento e a precisão são aplicados aos registros de competência. 

- **Configurar vários tipos de licença em um único plano de licença** - Uma nova coluna no plano de acumulação de licença para tipos de licença permite definir vários tipos de licença em um planejamento de licença e ausência com diferentes agendas de competência. O campo **Tipo de licença** anterior é removido. Na inscrição do funcionário, os saldos para os tipos de licença agora são exibidos em uma tabela em vez de na parte superior da tela.

  > [!IMPORTANT]
  > Não é possível desativar esse recurso após ativá-lo.

- **Use a equivalência de horário integral de um funcionário (FTE) para acumular** - Uma nova coluna na agenda de acumulação de licença permite o uso de FTE para acumulação. Quando as competências são processadas, o aplicativo usa a posição principal do funcionário e a FTE definida para determinar o valor acumulado rateado.

  > [!NOTE]
  > Este recurso só estará disponível se você habilitar **Configurar vários tipos de licença por licença**. 

## <a name="feedback"></a>Comentários

Queremos saber sua experiência com esses recursos de visualização. É recomendável postar regularmente seus comentários nos sites a seguir conforme você os usa ou quaisquer outros recursos:

- [Comunidade](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) Este site é um ótimo recurso onde os usuários podem discutir casos de uso, fazer perguntas e obter ajuda da comunidade.
- Conte para nós os recursos que você deseja ver no produto ou as alterações que você acha que devemos fazer nos recursos existentes. Sugerir ideias de produtos em [Ideias de Human Resources](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    
Não inclua dados pessoais (qualquer informação que pode te identificar) em seus comentários ou envios de análise do produto. Informações coletadas podem ser analisadas mais profundamente, e elas não serão usadas para atender a solicitações em leis aplicáveis de privacidade. Dados pessoais que são coletados separadamente nestes programas estão sujeitos à [Política de Privacidade online da Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Consulte também

- [Novidades em Human Resources](hr-admin-whats-new.md)
- [Dynamics 365 e Plano de versão do Power Platform](https://docs.microsoft.com/dynamics365/release-plans/#pivot=products&panel=products1)