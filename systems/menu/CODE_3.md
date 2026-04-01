# CREATE(CRIAR)

---

opcao = 0;

resolucoes = [
    [1024, 768],
    [1280, 720],
    [1920, 1080]
];

---

# STEP(ETAPA)

---

if (keyboard_check_pressed(vk_down)) opcao++;
if (keyboard_check_pressed(vk_up)) opcao--;

opcao = clamp(opcao, 0, array_length(resolucoes)-1);

if (keyboard_check_pressed(vk_enter)) {
    var w = resolucoes[opcao][0];
    var h = resolucoes[opcao][1];
    window_set_size(w, h);
}

if(keyboard_check_pressed(vk_escape)){room_goto(rm_menu_config)}

---

# DRAW(DESENHAR)

---

for (var i = 0; i < array_length(resolucoes); i++) {
    var xx = display_get_gui_width() / 2;
    var yy = display_get_gui_height() / 2 + i * 24;
    
    var texto = string(resolucoes[i][0]) + "x" + string(resolucoes[i][1]);
    
    draw_set_font(fnt_menu);
    
    if (i == opcao) draw_set_colour(c_red);
    else draw_set_colour(c_white);
    draw_set_font(fnt_menu);
    draw_set_valign(1);
    draw_text(xx, yy + (i * 40), texto);
    draw_set_valign(-1);
    draw_set_font(-1);
}
