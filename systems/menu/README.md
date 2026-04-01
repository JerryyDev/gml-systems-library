# 🖥️ Sistema de Menu (GML)

Sistema de menu funcional com navegação e configuração de resolução, pronto para uso em jogos 2D.

---

## 🚀 Funcionalidades

- Navegação com teclado (↑ ↓)
- Seleção com ENTER
- Submenu de configurações
- Alteração de resolução
- Retorno com ESC
- Estrutura simples e fácil de adaptar

---

## 🎥 Demonstração

> (coloque aqui um GIF ou vídeo mostrando o menu funcionando)

---

## 📂 Estrutura

- `obj_menu` → controla todo o menu
- Estados:
  - `0` → Menu principal
  - `1` → Configurações

---

## 🎮 Controles

- ↑ ↓ → navegar
- ENTER → selecionar
- ESC → voltar

---

## 💡 Como funciona

O sistema usa um controle de estados (`estado`) para alternar entre o menu principal e o menu de configurações.
As opções são armazenadas em arrays, facilitando a expansão do sistema.
