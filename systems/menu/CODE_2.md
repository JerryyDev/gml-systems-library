# CREATE(CRIAR)

---

opcoes = ["Resoluções"];
opcao_actual = 0;
OptionXS  = 1;
OptionYS  = 1;

---

# STEP(ETAPA)

---

if(keyboard_check_pressed(vk_down)){
    opcao_actual++;
}
if(keyboard_check_pressed(vk_up)){
    opcao_actual--;
}

if(opcao_actual > 0){
    opcao_actual = 0;
}
else if(opcao_actual < 0){
    opcao_actual = 0;
}

if(keyboard_check_pressed(vk_enter)){
    room_goto(rm_configs)
}

if(keyboard_check_pressed(vk_escape)){
    room_goto(Room1);
}

---

# DRAW(DESENHAR)

---

for (var i = 0; i < array_length(opcoes); i++) {
	
    var xx = display_get_gui_width() / 2;
    var yy = display_get_gui_height() / 2 + i * 24;
    
    if(i == opcao_actual){
        draw_set_colour(c_red);
    }
    
    draw_set_font(fnt_menu);
    draw_text_transformed(xx,yy,opcoes[i],OptionXS,OptionYS,0);
    draw_set_font(-1);
}

---

👉[Next CODE](./CODE_3.md)
