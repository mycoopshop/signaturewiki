1. http://xprocbook.com/book/chapter-1.html
1. https://www.w3.org/TR/xproc/
1. https://engineering.thetrainline.com/functional-programming-and-react-3a2a69b83d45
1. http://www.xml.com/pub/2000/09/13/xslt/index.html
1. https://docs.racket-lang.org/net/url.html
1. http://hc.apache.org/index.html
1. https://blogs.msdn.microsoft.com/dotnet/2017/07/24/get-started-with-f-as-a-c-developer/
1. https://docs.microsoft.com/en-us/dotnet/fsharp/style-guide/


An HTTP connection is created as a pure port or a impure port. A pure port is one from which the MIME headers have been removed, so that what remains is purely the first content fragment. An impure port is one that still has its MIME headers.

If you really want a pure function of that sort, then you need to pass in the time explicitly as a parameter.

    import System.Locale (defaultTimeLocale)
    import System.Time (formatCalendarTime, toUTCTime, getClockTime, ClockTime)

    main = do now <- getClockTime
           putStrLn $ getMonthString now

    getMonthString :: ClockTime -> String
    getMonthString = formatCalendarTime defaultTimeLocale "%B" . toUTCTime

Notice how getMonthString can be pure since the IO action getClockTime is performed elsewhere.