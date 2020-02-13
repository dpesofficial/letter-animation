# letter-animation

letterAnimation: function(){
            var tDelay = 0.005;
            var str = $('.intro-text h2').text();
            var result = "";
            str = str.split(" ");
            $.each(str, function () {
              result += '<span class="outer-span">';
              if (this.length > 0) {
                for (var index = 0; index < this.length; index++) {
                  result += '<span>' + this[index] + '</span>';
                  this[index]
                }
              }

              result += '&nbsp;</span>';
            });
            $('.intro-text h2').html($(result));
            $('body').find('.intro-text h2 span:not(.outer-span)').each(function(){
              $(this).css("transition-delay", tDelay + 's');
              tDelay = tDelay + 0.005;
            });

            var waypoints = $('.intro-text h2').waypoint(function(direction) {
              $(this.element).addClass('letters-animate');
            }, {
              offset: '100%'
            });

          }
