# `obj_menu`
## CREATE(CRIAR)
---
menu_text = ["PLAY", "CONFIGS", "QUIT"];
atual = 0;
menu_scale = array_create(array_length(menu_text), 1);

tittle = "Titulo Do Jogo";

title_x = display_get_gui_width() / 2;

title_y = display_get_gui_height() / 2 - 220;

title_time = 0;

xscale_tittle = 1;
yscale_tittle = 1;
---
## STEP(ETAPA)
---
title_time += 0.02;

if (keyboard_check_pressed(vk_down)) {
    atual++;
}

if (keyboard_check_pressed(vk_up)) {
    atual--;
}

if(atual == 0){
    if(keyboard_check_pressed(vk_enter))
        room_goto(rm_jogo);
}
if(atual == 1){
    if(keyboard_check_pressed(vk_enter))
        room_goto(rm_menu_config);
}
if(atual == 2){
    if(keyboard_check_pressed(vk_enter))
         game_end();
}

atual = clamp(atual, 0, array_length(menu_text) - 1);
---
## DRAW(DESENHAR)
---
draw_set_halign(fa_center);
draw_set_valign(fa_middle);
draw_set_font(fnt_menu);

for (var i = 0; i < array_length(menu_text); i++) {

    var xx = display_get_gui_width() / 2;
    var yy = display_get_gui_height() / 2 + i * 48;

    if (atual == i) {
        menu_scale[i] = lerp(menu_scale[i], 2, 0.15);
        draw_set_color(c_red);
    } else {
        menu_scale[i] = lerp(menu_scale[i], 1, 0.15);
        draw_set_color(c_white);
    }

    draw_text_transformed(
        xx,
        yy,
        menu_text[i],
        menu_scale[i],
        menu_scale[i],
        0
    );
}

draw_set_color(c_white);


var float_x = sin(title_time) * 12;
var float_y = cos(title_time * 1.3) * 8;

var scale = 3 + sin(title_time * 2) * 0.1;

draw_set_halign(fa_center);
draw_set_valign(fa_middle);
draw_set_font(fnt_menu);
draw_set_color(c_white);

draw_text_transformed(
    title_x + float_x,
    title_y + float_y,
    tittle,
    scale,
    scale,
    0
);

---

👉[Next CODE](./CODE_2.md)
