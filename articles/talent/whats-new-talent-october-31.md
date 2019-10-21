---
title: Novidades ou alterações no Dynamics 365 Talent - Core HR (31 de outubro de 2018)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
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
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d2ad9be740d917a760815718a1473d7bcba97968
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025923"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-31-2018"></a>Novidades ou alterações no Dynamics 365 Talent: Core HR (31 de outubro de 2018)

[!include [banner](includes/banner.md)]

**Compilação 8.1.2031**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="create-links-from-talent-to-finance"></a>Criar links do Talent ao Finance
Essa nova funcionalidade de navegação permite que você vincule o Talent ao Finance, oferecendo a você navegação direta nas páginas do Finance. Quando os links são configurados, você pode especificar o nome e o grupo do link, onde o link deve aparecer no Talent, e a página de destino a ser aberta no Finance.

#### <a name="coming-soon"></a>Em breve
O contexto de campo será adicionado no futuro para permitir a navegação direta aos registros correspondentes no Finance. Por exemplo, você pode usar **Link para campo** para fornecer o contexto para navegar diretamente a um funcionário ou a uma posição específica no Finance.

### <a name="configure-target-systems"></a>Configurar sistemas de destino

No Talent, administradores do sistema podem definir links que serão exibidos por meio do espaço de trabalho do Sistema de administração. Parte da configuração são os ambientes do Finance para os quais você deseja navegar como o "destino" do link. Você faz isso dando ao sistema de destino um nome e fornecendo a URL de ambiente do Finance. Veja este exemplo de uma URL do Finance que você forneceria: https://devax00124aos.cloud.test.dynamics.com/. Após configurar sistemas de destino, você pode definir os links.

### <a name="configure-links"></a>Configurar links

Cada link criado terá as seguintes informações definidas.

- Link - nome do link, usado somente para a identificação.

- Habilitar esse link - Defina para **Sim** para exibir o link para os usuários do Talent.

- Nome para exibição - Defina o nome que parecerá como um link para o Finance. Esses dados não são traduzidos no momento.

- Link de superfície no formulário - Escolha qual página gostaria de exibir o link.

- Grupo - Grupos não são necessários, mas se quiser organizar seus links usando grupos, selecione um grupo existente ou crie um novo usando o campo **Grupo**.

- Sistema de destino - Selecione o sistema de destino criado usando a opção **Configurar o sistema de destino**. Este será o ambiente do Finance que será usado ao navegar usando o link.

- Use a empresa atual de usuário - Selecione **Sim** se deseja usar o contexto da empresa atual do usuário ao navegar para o Finance. Se **Não** for selecionado, você poderá selecionar a empresa que deverá ser usada.

- Item de menu de destino - Digite o item de menu do Finance que o link deve usar ao navegar. Itens de menu onde você pode navegar diretamente estão disponíveis. Para localizar o item de menu obrigatório, abra o Finance e a página que é o destino da navegação. Copie o item de menu da URL. Por exemplo, se desejar que o link execute a lista de funcionários em Finance and Operations, insira o valor que surge após "&mi" na URL. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. O item de menu para navegar para a página de listagem de funcionário neste exemplo é: HcmWorkerListPage_Employees.

- Link para fonte de dados - selecione a fonte de dados com o qual o link está fazendo referência. As origens mais comuns como **Trabalhador** e **Posição** estão disponíveis.

- Link para campo (Em breve) - Este campo permitirá a navegação direta de um único registro no Talent a um único registro no Finance.

### <a name="access-to-links"></a>Acesso a links

Os administradores de sistema verão links recém-criados em páginas definidas se a opção **Habilitar esse link** estiver definida como **Não**. Isso pode ser usado antes testando links para aparecerem para outros funcionários. Todas funções restantes considerarão links configurados somente depois que a opção **Habilitar esse link** estiver definida como **Sim**. Os funcionários que têm acesso a páginas dos links terão acesso aos links.

Os usuários também podem ter direitos de segurança no Finance definidos para acessar as páginas no Finance and Operations. Se não tiverem, uma caixa de diálogo de segurança será exibida usando o link.


## <a name="other-changesfixes"></a>Outras alterações/correções

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>Posições com uma data inicial futura não podem ser atribuídas a um novo funcionário

As alterações foram feitas para permitir atribuições de funcionário a posições datadas futuras. Posições que têm datas iniciais no futuro podem ser selecionadas e a atribuição de funcionário será feita ao salvar ou ao concluir o fluxo de trabalho (se o fluxo de trabalho for habilitado).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>O novo funcionário não pode ser atribuído à posição existente

As alterações foram feitas para que a nova atribuição de funcionários possa ser atribuída a cargos existentes.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>A data de tempo de trabalho/local de escritório desaparece quando a data de início do emprego está no passado e o registro está salvo.

As alterações foram feitas para corrigir a visibilidade de **Data de tempo de trabalho** e **Localização do escritório** quando salvar para funcionários passados.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>Não pode inserir dados para empregos futuros datados na página de trabalho

Os dados de emprego para empregos de datas futuras foram desativados na página principal do trabalhador. Os dados de emprego podem ser inseridos em páginas do **Gerente da data**. Alterações adicionais serão feitas em versões futuras para habilitar inserção de dados de emprego diretamente durante o processo de fluxo de trabalho.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>Adicionar ValidFrom e ValidTo to HcmPersonalContactPersonEntity

A entidade de Data Management Framework (DMF) HcmPersonalContactPersonEntity foi atualizada para incluir datas de "válido de" e "válido até" para habilitar certos cenários de integração de benefício. 

## <a name="known-issue"></a>Problema conhecido
- **Erro**: Ao adicionar um novo anexo a um trabalhador, os botões **Novo** e **Editar** são esmaecidos. 
- **Solução alternativa:** Antes de abrir a página do anexo, garante que os caixas de dados na página **Trabalhador** estejam fechadas. Se os Quadros de Fatos estiverem fechados quando a página **Trabalhador** for carregada, os botões Anexos serão habilitados. (Esse problema será corrigido na próxima atualização de plataforma.)
