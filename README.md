# vim_swap_line

You could move current line up or down, and the position of the cursor won't change. 

你可以把当前行上移/下移, 并且不会改变光标所在位置.



To do this, you only need to add the following code into your `vimrc`.

为了实现下列操作, 你只需要把下列代码放入你的`vimrc`中.

```
" #################### Don't change this ####################
function Fau_move_line_down()
	let pos = getpos('.')[1:]
	let pos[0] = pos[0] + 1

	execute 'normal! ddp'
	call cursor(pos)	
endfunction

function Fau_move_line_up()
	let pos = getpos('.')[1:]
	let pos[0] = pos[0] - 1

	execute 'normal! kddp'
	call cursor(pos)	
endfunction
" #################### Don't change this ####################



" Here is your customization
" You can map <A-j> and <A-k> to any key you like.

noremap <silent> <A-j> :call Fau_move_line_down()<CR> 
noremap <silent> <A-k> :call Fau_move_line_up()<CR>
```

