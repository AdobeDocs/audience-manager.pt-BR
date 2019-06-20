---
source-git-commit: dee392312d8e0381c714a99b5d537c767107c9bc
translation-type: tm+mt

---
# Instruções

**Observação: Esta página (ou qualquer página readme. md) não será publicada na documentação voltada para o cliente**

## Sumário

+ `TOC.md` na raiz do guia do usuário fornece a organização dos tópicos contidos no guia para esta solução.
+ Each user guide will have its own unique `TOC.md`, in which you can order all the pages/topics as necessary.
+ The first page of all user guides is `overview.md`.

## Guia do usuário

+ The introduction to the user guide is called `overview.md`
+ Cada tópico no guia do usuário tem seu próprio diretório distinto.
   + If there is a topic in the guide called *Implementation*, the corresponding directory is `/implementation`
+ All image assets are stored in `/assets` at the root of the user guide.
   + All images in the `/assets` directory will be localized.
   + Any images in the `/no-localize` directory will not be localized (there&#39;s a surprise!). Isso pode ser usado para garantir em versões loc que os ativos específicos não serão reproduzidos desnecessariamente.

## Metadados de nível do guia do usuário

+ Meta data which describes the user guide is stored in the `TOC.md`. Isso inclui:
   + produto - nome do produto/recurso.
   + nuvem - nuvem à qual este produto pertence.
   + público-alvo: público-alvo ou arquivema no qual o guia é direcionado.
   + guia do usuário - nome do guia do usuário.

## Metadados de nível de página

+ Os metadados necessários para descrever um documento são armazenados como parte de cada página individual. Isso inclui:
   + título - título da página.
   + descrição - descrição da página.
   + seo-title - título alternativo seo.
   + seo-description - título alternativo para fins de SEO.
   + abreviado - (campo opcional).
   + index - sim/não - a página será indexada pela plataforma de pesquisa da Adobe.
   + traduzir - sim/não - essa página será localizada.
   + versão - usada principalmente para o AEM e Campanha, para indicar a versão do produto.
   + private-feature-pack - usado principalmente para o AEM.
   + beta - este produto é beta?
   + redirecionar - pode ser usado para criar um ref para uma nova página, se necessário.
   + doc-type: reference (padrão)/troubleshooting/developer/tutorial/kb/whitepaper.

## Mais Informações

For more publishing instructions, style guides, samples and other resources, please visit the [Collaborative Documentation Repo](https://git.corp.adobe.com/AdobeDocs/collaborative-doc-instructions)
