---
title: Inserir dados do candidato e da solicitação de emprego manualmente
description: Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego.
author: twheeloc
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d59b5a2c99813fee2e12e30e8694edf6da7391d9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909239"
---
# <a name="enter-applicant-and-application-data-manually"></a>Inserir dados do candidato e da solicitação de emprego manualmente

> [!NOTE]
> A funcionalidade de recrutamento neste artigo será referida como Projetos de recrutamento e se concentra em candidatos, solicitações de emprego e projetos de recrutamento.  


Este procedimento mostra como manter manualmente as informações sobre os candidatos e a solicitação de emprego. Você pode inserir e manter as informações pessoais, as datas e os horários de entrevista, as referências, as competências e as solicitações de acomodação para candidatos. Você também pode atualizar o status das ordens de candidatos de emprego e criar cartas ou mensagens de email para comunicar-se com os candidatos. Quando você criar um registro do candidato, um registro para o candidato é criado no catálogo de endereços global. A empresa de dados de demonstração **USMF** foi usada para criar este procedimento.

## <a name="create-a-new-applicant-record"></a>Criar um novo registro de candidato

1. Acesse **Recursos humanos \> Recrutamento \> Candidatos \> Candidatos**.
2. Selecione **Novo**.
3. No campo **Nome**, insira um valor.
4. No campo **Sobrenome**, insira um valor.

    Você pode inserir informações adicionais do candidato se estiver disponível. Por exemplo, essas informações podem incluir o nível mais alto do candidato, a posição atual ou o empregador anterior.

5. Expanda a seção **Informações do contato**.
6. Selecione **Adicionar**.
7. No campo **Descrição**, insira **Email de comunicação**.
8. No campo **Tipo**, selecione uma opção.
9. No campo **Número/endereço do contato**, insira um valor.

    Este endereço de email será usado para gerar comunicação de email com o candidato.

10. Selecione **Adicionar**.
11. No campo **Descrição**, insira um valor.
12. No campo **Número/endereço do contato**, insira um valor.

    Use esse campo para inserir informações pessoais adicionais sobre o candidato, conforme necessário. Por exemplo, essas informações podem incluir a data de nascimento, a origem étnica, o gênero ou o estado civil do candidato.

13. No Painel de Ações, selecione **Competências**.

    Você pode inserir o perfil de competência do candidato, incluindo suas experiências, habilidades profissionais, formação educacional, testes ou os certificados. Essas informações podem ser usadas para mapear habilidades do candidato às habilidades associadas ao trabalho definidas nos dados da empresa.

## <a name="create-an-application-for-the-applicant"></a>Crie uma solicitação de emprego para o candidato

1. Selecione **Solicitações de emprego**.
2. Selecione **Novo**.
3. No campo **Projeto de recrutamento**, selecione a seta suspensa para abrir a pesquisa.

    Selecionando um projeto de recrutamento, você garante que o candidato será associado a uma determinada abertura incluída no projeto de recrutamento.

4. Na lista, localize e selecione o registro desejado.
5. Na lista, selecione o link na linha selecionada.

    Por padrão, os trabalhos e o departamento são baseados no projeto de recrutamento selecionado.

6. Selecione **Salvar**.

    Depois de salvar a solicitação de emprego, você pode anexar documentos a ele. Esses documentos podem incluir a experiência, os prêmios e a carta de apresentação do candidato.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
