<div align="center">
  <img src="assets/logo_highmed_verde.webp" alt="Score 100 PageSpeed" width="600" />
  
  <br />
  <br />

  # ⚡ Highmed | Case de Performance Extrema
  **Estudo de Caso: Landing Page de Alta Conversão com Core Web Vitals Gabaritado**

  <p align="center">
    <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
    <img src="https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E" alt="Vite" />
    <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind CSS" />
    <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
    <img src="https://img.shields.io/badge/PageSpeed-100%2F100-success?style=for-the-badge&logo=google" alt="PageSpeed 100" />
  </p>
</div>

---

## 🔒 Status do Repositório (Confidencialidade)

**Este é um repositório de Showcase (Vitrine).** O projeto real foi desenvolvido profissionalmente para a **Highmed**. Em respeito às políticas de NDA (Non-Disclosure Agreement) e à propriedade intelectual do cliente, o código-fonte original é mantido em um repositório privado. 

Este documento serve como um **estudo de caso técnico** detalhando a arquitetura e as soluções de engenharia aplicadas para atingir o nível máximo de performance. 

Você pode conferir o resultado final e testar a velocidade diretamente na produção:
🔗 **[Acessar o Site em Produção](https://www.highmedeletrica.com.br)**

---

## 🎯 O Desafio

Criar uma interface moderna para o setor de energia (VLF, Tangente Delta e Termografia), rica em animações (Framer Motion) e interações, sem sacrificar a performance. O objetivo comercial era atingir a nota máxima no Google PageSpeed Insights (Mobile e Desktop) para dominar o SEO técnico e reduzir a taxa de rejeição (Bounce Rate).

---

## 🚀 O "Gabarito" de Performance (Core Web Vitals)

A engenharia do Front-end foi focada em garantir que o navegador trabalhasse a meu favor. Os resultados auditados em produção foram:

* 🟢 **LCP (Largest Contentful Paint) < 2.5s:** Otimização cirúrgica da entrega de imagens (WebP com dimensionamento exato da logo em 336x224), e uso estratégico de `fetchpriority="high"` na dobra superior.
* 🟢 **INP (Interaction to Next Paint) < 200ms:** Eliminação completa de "congelamentos" de tela e sequestro da Main Thread. Botões do Hero respondem instantaneamente.
* 🟢 **CLS (Cumulative Layout Shift) = 0:** Layout perfeitamente estável. Espaços pré-reservados com `aspect-ratio` garantem que nada sofra mutação durante o carregamento.
* 🟢 **TBT (Total Blocking Time) = 0ms:** A thread principal desobstruída aplicando técnicas cirúrgicas de Code Splitting.

---

## 🧠 Arquitetura & Soluções Técnicas

Para alcançar o 100/100 no ecossistema React/Vite, as seguintes otimizações pesadas foram aplicadas:

### 1. Code Splitting & Hidratação Passiva (`requestIdleCallback`)
O bundle monolítico foi quebrado. O Header e o Hero carregam de forma síncrona. O restante da página (formulários, rodapé, seções de confiança) é injetado "invisivelmente" apenas quando a CPU do celular do usuário relata ociosidade, blindando a primeira interação (INP).

### 2. Zero CSS Blocking
Configuração do Vite para inlining de CSS crítico (`vite-plugin-css-injected-by-js`). Isso eliminou o bloqueio de renderização causado por requisições de rede externas, antecipando o FCP.

### 3. Eliminação de "Forced Reflow"
Listeners de `scroll` sincronizados com o ciclo nativo de pintura do monitor através de `window.requestAnimationFrame`, zerando o estresse na placa de vídeo e evitando recálculos de geometria síncronos.

### 4. Yield to Main Thread
Padrões de delegação de tarefas (encapsulamento em `setTimeout` e `startTransition`) para devolver o controle à Main Thread rapidamente, permitindo que o navegador processe o feedback visual sem gargalos.

---

## 🛠️ Stack Tecnológico

* **Core:** React 18, TypeScript, Vite
* **UI & Estilização:** Tailwind CSS, Radix UI
* **Animações:** Framer Motion (`LazyMotion` para motor sob demanda)
* **Gerenciamento:** React Query, React Router DOM
* **Performance:** Vercel Speed Insights & Analytics

---

## 👨‍💻 Autor

**Felipe Scudiero**
*Desenvolvedor Front-end*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/devscud/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Fehscudiero)
