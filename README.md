# cgan-mw-decoupling-data

    phase_lam1 = double( imread( [ image_path1 filesep 'phantom_phase_505nm_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
    phase_lam2 = double( imread( [ image_path3 filesep 'phantom_phase_488nm_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
    n_true = double( imread( [ image_path3 filesep 'phantom_index_505nm_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
   %  n_true = double( imread( [ 'C:\Users\bazowbs1\Documents\CUA\cnn_decoupling\python\cgan\decoupled_images_256_v1\decoupled_images\new_index' filesep 'phantom_index_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
