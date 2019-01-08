# salt_win
saltstack for windows

http.query module can't post binary file.
So I have modified http.py to post binary file.
The changed code is following as:

    if data_file is not None:
        if salt.utils.files.is_binary(data_file):
            with salt.utils.files.fopen(data_file, 'rb') as fh_:
                data = fh_.read()
        else:
            data = _render(
                data_file, data_render, data_renderer, template_dict, opts
            )

Thank you.
