http://xprocbook.com/book/chapter-1.html
https://www.w3.org/TR/xproc/
https://engineering.thetrainline.com/functional-programming-and-react-3a2a69b83d45
http://www.xml.com/pub/2000/09/13/xslt/index.html
https://docs.racket-lang.org/net/url.html

An HTTP connection is created as a pure port or a impure port. A pure port is one from which the MIME headers have been removed, so that what remains is purely the first content fragment. An impure port is one that still has its MIME headers.

If you really want a pure function of that sort, then you need to pass in the time explicitly as a parameter.

    import System.Locale (defaultTimeLocale)
    import System.Time (formatCalendarTime, toUTCTime, getClockTime, ClockTime)

    main = do now <- getClockTime
           putStrLn $ getMonthString now

    getMonthString :: ClockTime -> String
    getMonthString = formatCalendarTime defaultTimeLocale "%B" . toUTCTime

Notice how getMonthString can be pure since the IO action getClockTime is performed elsewhere.