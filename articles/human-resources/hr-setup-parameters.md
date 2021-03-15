---
title: Configurar parâmetros de recursos do Human Resources
description: As configurações de alguns parâmetros de Recursos humanos são compartilhadas entre empresas, enquanto as configurações de outros parâmetros são específicas. Este artigo explica como configurar parâmetros de RH específicos da empresa.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 131606ebaff49a2c63d22bcfdb5e523f4df87ec6
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129116"
---
# <a name="configure-human-resources-parameters"></a>Configurar parâmetros de recursos do Human Resources

As configurações de alguns parâmetros de Recursos humanos (RH) são compartilhadas entre empresas, enquanto as configurações de outros parâmetros são específicas. Este artigo explica como configurar parâmetros de RH específicos da empresa.

Duas páginas são usadas para definir os parâmetros de recursos humanos (RH). Para os parâmetros que são compartilhados entre empresas, use a página **Parâmetros compartilhados de recursos humanos**. Para os parâmetros que são específicos da empresa (ou seja, as configurações se aplicam a uma única empresa), use a página **Parâmetros de recursos humanos**. Na página **Parâmetros de recursos humanos**, as configurações são divididas entre seis guias:

-   Geral
-   Recrutamento - isso não está incluído no Dynamics 365 Human Resources
-   Remuneração
-   Sequências numéricas
-   Lei de família de licença e médica (FMLA)
-   Autoatendimento para funcionários

Cada guia contém informações que pertencem a uma única empresa. As configurações na guia **Geral** definem a aparência das informações sobre ausência, lesões e doenças, e novas contratações. As configurações nessa guia também definem algumas entradas padrão que aparecem enquanto você trabalha. Especificamente, essa guia permite que você selecione uma cor a ser aplicada às transações de ausência abertas, especifique a folha de estilos a ser usada nos relatórios, habilite a integração entre cursos de treinamento e registro de ausência, e selecione o código de ausência a ser usado para controlar essa integração. Você também pode indicar o período em que os incidentes de caso de lesões e doenças devem ser mantidos, e especificar o número de identificação padrão mostrado quando um novo trabalhador é contratado. 

As configurações na guia **Recrutamento** definem os tipos de documentos usados para correspondência que são enviados automaticamente a candidatos, e o projeto de recrutamento usado em solicitações de emprego não solicitadas (as solicitações de emprego que não se referem a um projeto de recrutamento específico). O período definido para o vencimento do projeto de recrutamento determina os projetos de recrutamento incluídos no bloco **Projetos de vencimento** no espaço de trabalho **Gerenciamento de recrutamento**. O período definido para o aviso de prazo da solicitação de emprego é usado para exibir os projetos de recrutamento que estão se aproximando do prazo no bloco **Prazo final para solicitação de emprego se aproximando** no espaço de trabalho **Recrutamento**. 

As configurações na guia **Compensação** definem se os usuários devem confirmar que desejam salvar informações para um plano de remuneração fixo ou variável. Se você marcar a caixa de seleção **Habilitar validação ao salvar**, a qualquer momento que os usuários fecham uma página relacionada à compensação, eles recebem uma mensagem que pergunta se eles querem salvar o registro. Algumas páginas no gerenciamento de compensações não permitem que os usuários excluam informações. Portanto, ao solicitar que os usuários verifiquem se desejam salvar informações, é possível limitar a quantidade de informações que serão salvas, mas não poderão ser excluídas posteriormente. Se a caixa de seleção **Permitir salvar validação** estiver desmarcada, os registros serão salvos imediatamente, possivelmente antes que o usuário esteja pronto. Se você estiver usando o gerenciamento de desempenho, a guia **Remuneração** também permitirá que você selecione um modelo de avaliação a ser usado em vez do modelo atribuído aos planos de remuneração quando o desempenho é avaliado. 

### <a name="previously-released-functionality"></a>Funcionalidade liberada anteriormente

As configurações na guia **Sequência numérica** determinam as sequências usadas para atribuir automaticamente IDs a itens em Recursos humanos, como solicitações de emprego, registros de ausência, resultados do processo de remuneração, números de casos, cursos e agendas de curso. Para manter referências e códigos de sequência de números, use a página de listagem **Sequências numéricas** (clique em **Administração organizacional** &gt; **Sequências numéricas** &gt; **Sequências numéricas**).

> [!NOTE]
> O número de horas que será trabalhado não pode exceder 1.250 e o tempo de emprego não pode exceder 12 meses. Esses valores máximos estão de acordo com a legislação federal dos Estados Unidos. Por fim, as configurações na guia **Autoatendimento para funcionários** determinam as informações que gerentes pode inserir em nome dos funcionários.


[!INCLUDE[footer-include](../includes/footer-banner.md)]