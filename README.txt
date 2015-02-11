=== Yii Bootstrap NavBar - Brand Logo ===

Added an additional class for the NavBar 'Brand' section - $brandLogo
This can be called and used to echo an image URL in the NavBar brand section.

=== installation === 

Replace current bootstrap NavBar.php with the current one in the repo.

location within Yii Basic project:

../vendor/yiisoft/yii2-bootstrap/NavBar.php


Once replaced, the $brandLogo class can be added to the NavBar in your layout:

		<?php
            NavBar::begin([
                'brandLogo' => ' IMAGE URL HERE ',
                'brandLabel' => '&nbsp;' . 'ionCube', 
                'brandUrl' => Yii::$app->homeUrl,
                'options' => [
                    'class' => 'navbar-inverse navbar-fixed-top',
                ],
            ]);
            echo Nav::widget([
                'options' => ['class' => 'navbar-nav navbar-right'],
                'items' => [
                    ['label' => 'Home', 'url' => ['/site/index']],
                    ['label' => 'About', 'url' => ['/site/about']],
                    ['label' => 'Contact', 'url' => ['/site/contact']],
                    Yii::$app->user->isGuest ?
                        ['label' => 'Login', 'url' => ['/site/login']] :
                        ['label' => 'Logout (' . Yii::$app->user->identity->username . ')',
                            'url' => ['/site/logout'],
                            'linkOptions' => ['data-method' => 'post']],
                ],
            ]);
            NavBar::end();
        ?>
		
you cna align the image left if you with have it inline with the usual $brandLabel in the NavBar brand section.