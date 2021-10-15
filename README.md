# cgan-mw-decoupling-data

    # read true phase at each wavelength in matlab
    phase_lam1 = double( imread( [ root filesep 'phase2phase' filesep 'phantom_phase_505nm_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
    phase_lam2 = double( imread( [ root filesep 'phase2phase' filesep 'phantom_phase_488nm_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
    
    # read predicted phase at wavelength 2 in matlab (first execute pix2pix in https://github.com/bazowbs1/cgan-mw-decoupling)
    phase_lam2_predict = double( imread( [ root filesep 'predict_' num2str( nEpochs ) '_epochs' filesep num2str( frames( ii ) ) '_predict.tif' ] ) );
    
    # read true refractive index and height in matlab
    n_true = double( imread( [ root filesep 'refractiveIndex' filesep 'phantom_index_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
    hz_true = double( imread( [ root filesep 'height' filesep 'phantom_height_' num2str( frames( ii ) ) '.tif' ] ) )*1e-6;
 
    # alternativley the refractive index and height can be decoupled from the true phase at each wavelength
    n01 = 1.33; n02 = 1.35;
    opl_lam1 = lambda1*phase_lam1/( 2*pi );
    opl_lam2 = lambda2*phase_lam2/( 2*pi );
    n_true = n01+opl_lam1*( n02-n01)./( opl_lam1-opl_lam2);
    hz_true = ( opl_lam1-opl_lam2 )/( n02-n01 );
